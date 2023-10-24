<template>
  <div>
    <section
      class="vh-140 bg-image"
      style="background-color: #d9d9d9; padding: 3px 0"
    >
      <div class="mask d-flex align-items-center h-100 gradient-custom-3">
        <div class="container h-100">
          <div
            class="row d-flex justify-content-center align-items-center h-100"
          >
            <div class="col-12 col-md-9 col-lg-7 col-xl-6">
              <div class="card" style="border-radius: 15px">
                <div class="card-body p-5">
                  <h2 class="text-uppercase text-center mb-5">
                    Login
                  </h2>

                  <form
                    id="form-pengguna"
                    @submit.prevent="onFormLoginPengguna()"
                  >
                    <div class="form-outline mb-4">
                      <input
                        id="username"
                        v-model="username"
                        type="text"
                        class="form-control form-control-lg"
                      >
                      <label
                        class="form-label"
                        for="username"
                      >Input Your Username</label>
                    </div>
                    <!-- <div class="form-outline mb-4">
                          <input
                            id="nama"
                            type="text"
                            class="form-control form-control-lg"
                          >
                          <label
                            class="form-label"
                            for="nama"
                          >Input Your Name</label>
                        </div> -->

                    <div class="form-outline mb-4">
                      <input
                        id="email"
                        v-model="email"
                        type="email"
                        class="form-control form-control-lg"
                      >
                      <label
                        class="form-label"
                        for="email"
                      >Input Your Email</label>
                    </div>

                    <div class="form-outline mb-4">
                      <input
                        id="password"
                        v-model="password"
                        type="password"
                        class="form-control form-control-lg"
                      >
                      <label
                        class="form-label"
                        for="password"
                      >Input Password</label>
                    </div>

                    <!-- <div class="form-outline mb-4">
                      <input
                        id="alamat"
                        v-model="alamat"
                        type="text"
                        class="form-control form-control-lg"
                      >
                      <label
                        class="form-label"
                        for="alamat"
                      >Input Alamat</label>
                    </div> -->
                    <!-- <div class="form-outline mb-4">
                      <input
                        id="no_hp"
                        v-model="no_hp"
                        type="tel"
                        class="form-control form-control-lg"
                      >
                      <label class="form-label" for="no_hp">Input No Hp</label>
                    </div> -->

                    <!-- <div class="form-check d-flex justify-content-center mb-5">
                          <input
                            id="form2Example3cg"
                            class="form-check-input me-2"
                            type="checkbox"
                            value=""
                          >
                          <label class="form-check-label" for="form2Example3g">
                            I agree all statements in
                            <a
                              href="#!"
                              class="text-body"
                            ><u>Terms of service</u></a>
                          </label>
                        </div> -->

                    <div class="d-flex justify-content-center">
                      <button
                        type="submit"
                        class="btn btn-success btn-block btn-lg gradient-custom-4 text-body"
                        @click="onLogin()"
                      >
                        Login
                      </button>
                      <!-- <a class="small text-muted" href="#!">Forgot password?</a> -->
                    </div>
                    <p class="mb-5 pb-lg-2" style="color: #393f81;">
                      Don't have an account? <a
                        href="/app/form/register"
                        style="color: #393f81;"
                      >Register here</a>
                    </p>

                    <!-- <p class="text-center text-muted mt-5 mb-0">
                          Have already an account?
                          <a
                            href="/login"
                            class="fw-bold text-body"
                          ><u>Login here</u></a>
                        </p> -->
                  </form>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
export default {
  data () {
    return {
      pengguna: [],
      username: ' ',
      email: ' ',
      password: 0,
      alamat: ' ',
      no_hp: 0
    }
  },
  mounted () {
    // const username = this.dataForm?.userame
    this.onFormLoginPengguna()
    // console.log(username)
  },
  methods: {
    async onFormLoginPengguna () {
      const dataForm = {
        username: document.getElementById('username').value,
        email: document.getElementById('email').value,
        password: document.getElementById('password').value
        // alamat: document.getElementById('alamat').value,
        // no_hp: document.getElementById('no_hp').value
      }
      // console.log(dataForm)
      const response = await fetch(
        `https://jylpaciooxarhelwslji.supabase.co/rest/v1/pengguna?username=eq.${dataForm.username}`,
        {
          headers: {
            apikey:
              'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU'
          }
        }
      )
      const data = await response.json()
      // //   console.log(data)
      // console.log(data)
      this.username = data[0]?.username
      this.email = data[0]?.email
      this.password = data[0]?.password
      this.alamat = data[0]?.alamat
      this.no_hp = data[0]?.no_hp
      // eslint-disable-next-line eqeqeq
      // if (dataForm.username !== undefined) {
      //   return this.$router.push(`/app/profile/${dataForm.username}`)
      // }
    },
    onLogin () {
      this.$router.push(`/app/profile-user/${this.username}`)
    }
  }

  // async onFormLoginPengguna () {
  //   //   const tambahProducts = document.getElementById('tambah-products')
  //   //   // eslint-disable-next-line no-use-before-define, new-cap
  //   //   const formData = new formData(tambahProducts)
  //   const dataForm = {
  //     username: document.getElementById('username').value,
  //     email: document.getElementById('email').value,
  //     password: document.getElementById('password').value,
  //     alamat: document.getElementById('alamat').value,
  //     no_hp: document.getElementById('no_hp').value
  //   }
  //   console.log(dataForm)
  //   const response = await fetch(
  //     `https://jylpaciooxarhelwslji.supabase.co/rest/v1/pengguna?username=eq.${this.username}`,
  //     {
  //       method: 'PATCH',
  //       headers: {
  //         apiKey:
  //           'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU',
  //         'Content-Type': 'application/json',
  //         Prefer: 'return=representation'
  //       },
  //       body: JSON.stringify(dataForm)
  //     }
  //   )
  //   // console.log(await response?.json())
  //   const data = await response?.json()
  //   console.log(data)
  //   this.$router.push(`/app/profile/${data[0]?.username}`)
  // }
}

</script>
<style scoped>
.gradient-custom-3 {
  /* fallback for old browsers */
  background: #84fab0;

  /* Chrome 10-25, Safari 5.1-6 */
  background: -webkit-linear-gradient(
    to right,
    rgba(208, 208, 208, 0.5),
    rgba(218, 218, 218, 0.5)
  );

  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  background: linear-gradient(
    to right,
    rgba(255, 255, 255, 0.5),
    rgba(143, 211, 244, 0.5)
  );
}
.gradient-custom-4 {
  /* fallback for old browsers */
  background: #17b6e2;

  /* Chrome 10-25, Safari 5.1-6 */
  background: -webkit-linear-gradient(
    to right,
    rgba(132, 250, 176, 1),
    rgba(143, 211, 244, 1)
  );

  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  background: linear-gradient(
    to right,
    rgb(60, 214, 155),
    rgb(47, 174, 238)
  );
}
</style>
