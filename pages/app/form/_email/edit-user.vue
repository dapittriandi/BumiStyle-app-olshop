<template>
  <div>
    <section
      class="vh-140 bg-image"
      style="background-color: #3877ff; padding: 3px 0"
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
                    Edit Profile
                  </h2>

                  <form
                    id="form-pengguna"
                    @submit.prevent="onFormEditPengguna"
                  >
                    <input
                      id="id"
                      v-model="penggunaId"
                      name="id"
                      type="hidden"
                      class="form-control"
                    >
                    <div class="form-outline mb-4">
                      <label
                        class="form-label"
                        for="username"
                      >Input Your Username</label>
                      <input
                        id="username"
                        v-model="username"
                        type="text"
                        class="form-control form-control-lg"
                      >
                    </div>
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

                    <div class="form-outline mb-4">
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
                    </div>
                    <div class="form-outline mb-4">
                      <input
                        id="no_hp"
                        v-model="no_hp"
                        type="tel"
                        class="form-control form-control-lg"
                      >
                      <label class="form-label" for="no_hp">Input No Hp</label>
                    </div>
                    <div class="d-flex justify-content-center">
                      <button
                        type="submit"
                        class="btn btn-success btn-block btn-lg gradient-custom-4 text-body"
                      >
                        Submit
                      </button>
                    </div>
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
  layout (context) {
    return 'CustomDefault'
  },
  data () {
    return {
      username: ' ',
      email: ' ',
      password: '',
      alamat: ' ',
      no_hp: 0,
      penggunaId: ''
    }
  },
  mounted () {
    const params = this.$route.params
    console.log(this.username)
    console.log(params?.username)
    this.getUserByUsername(params?.username)
  },
  methods: {
    async getUserByUsername (username) {
      const response = await fetch(
        `https://jylpaciooxarhelwslji.supabase.co/rest/v1/pengguna?username=eq.${username}`,
        {
          headers: {
            apikey:
              'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU'
          }
        })
      const data = await response.json()
      console.log(data)
      this.username = data[0]?.username
      this.email = data[0]?.email
      this.password = data[0]?.password
      this.alamat = data[0]?.alamat
      this.no_hp = data[0]?.no_hp
      this.penggunaId = data[0]?.id
    },
    async onFormEditPengguna () {
      try {
        const dataFormPengguna = {
          username: document.getElementById('username').value,
          email: document.getElementById('email').value,
          password: document.getElementById('password').value,
          alamat: document.getElementById('alamat').value,
          no_hp: document.getElementById('no_hp').value,
          id: document.getElementById('id').value
        }
        console.log(dataFormPengguna)
        const response = await fetch(
        `https://jylpaciooxarhelwslji.supabase.co/rest/v1/pengguna?username=eq.${this.username}`,
        {
          method: 'PATCH',
          body: JSON.stringify(dataFormPengguna),
          mode: 'cors',
          headers: {
            apiKey:
              'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU',
            'Content-Type': 'application/json',
            Accept: '*/*',
            'Accept-Encoding': 'gzib, deflate, br',
            Prefer: 'return=representation',
            'Access-Control-Allow-Origin': '*',
            credentials: 'same-origin'
          }
          // body: JSON.stringify(dataForm)
        }
        )
        console.log(response)
        const data = await response?.json()
        // console.log(await result?.json())
        // const data = await response?.json()
        console.log(data)
        // this.$router.push(`/app/profile-user/${data[0]?.username}`)
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>
<style scoped>
.gradient-custom-3 {
  background: #84fab0;

  background: -webkit-linear-gradient(
    to right,
    rgba(132, 250, 176, 0.5),
    rgba(143, 211, 244, 0.5)
  );

  background: linear-gradient(
    to right,
    rgba(132, 250, 176, 0.5),
    rgba(143, 211, 244, 0.5)
  );
}
.gradient-custom-4 {
  background: #84fab0;

  background: -webkit-linear-gradient(
    to right,
    rgba(132, 250, 176, 1),
    rgba(143, 211, 244, 1)
  );

  background: linear-gradient(
    to right,
    rgba(132, 250, 176, 1),
    rgba(143, 211, 244, 1)
  );
}
</style>
