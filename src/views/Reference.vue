<template>
  <section class="vh-100" style="background-color: #00aaff">
    <div class="container h-100">
      <div class="row d-flex justify-content-center align-items-center h-100">
        <div class="col-lg-12 col-xl-11">
          <div class="card text-black" style="border-radius: 25px">
            <div class="card-body p-md-5">
              <div class="row justify-content-center">
                <div
                  class="col-md-10 col-lg-6 d-flex justify-content-center align-items-center col-xl-5 order-2 order-lg-1"
                >
                  <div class="row" v-if="ref">
                    <label for="inputEmail4">Your ID </label>
                    <div class="d-flex flex-row align-items-center mb-4">
                      <div class="form-outline flex-fill mb-0">
                        <input
                          type="text"
                          class="form-control"
                          id="inputEmail4"
                          :value="ref"
                          required
                          placeholder="Votre Referenciel???"
                          readonly
                        />
                      </div>
                    </div>
                    <router-link
                      :to="{ path: '/rdv/' + ref }"
                      class="btn btn-primary btnref"
                      tag="button"
                      >Login</router-link
                    >
                  </div>
                  <div v-else>
                    <label
                      for="inputEmail4"
                      class="text-center h2 fw-bold mx-1 mx-md-4 mt-4"
                      >Welcome to DABADOC</label
                    ><br /><br />
                    <input
                      type="text"
                      v-model="refl"
                      class="form-control"
                      id="inputEmail4"
                      placeholder="Your ID"
                      required
                    />
                    <button
                      class="btn btn-primary btn-lg btnref mt-3"
                      @click="search()"
                    >
                      Login
                    </button>
                    <div>
                      <p class="mt-5 pb-lg-2" style="color: #393f81">
                        Don't have an account ?
                        <router-link :to="{ path: '/Signup' }"
                          >Signup</router-link
                        >
                      </p>
                    </div>
                  </div>
                  <div class="alert alert-danger" role="alert" v-if="erreur">
                    {{ erreur }}
                  </div>
                </div>
                <div
                  class="col-md-10 col-lg-6 col-xl-7 d-flex align-items-center order-1 order-lg-2"
                >
                  <img
                    src="https://img.freepik.com/vecteurs-libre/cliente-visiteur-parlant-receptionniste-bureau-bulle-dialogue-illustration-vectorielle-plane-ordinateur-portable-service-communication_74855-13068.jpg?size=626&ext=jpg&ga=GA1.2.428865127.1649071668"
                    class="img-fluid"
                    alt="..."
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "Reference",
  data() {
    return {
      ref: "",
      refl: "",
      erreur: "",
    };
  },
  methods: {
    async search() {
      const response = await fetch(
        "http://localhost/brief-6/back-end/api/User/Signin/" + this.refl
      );
      const data = await response.json();

      if (data.message) {
        this.erreur = data.message;
        console.log(this.erreur);
      } else {
        this.$router.push("/rdv/" + this.refl);
      }
    },
  },
  mounted: function () {
    this.ref = this.$route.params.ref;
  },
};
</script>