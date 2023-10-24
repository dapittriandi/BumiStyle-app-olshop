<template>
  <div>
    <section
      class=""
      style="
        background-color: #3877ff;
        padding: 3px 0;
      "
    >
      <div class="mask d-flex align-items-center gradient-custom-3">
        <div class="container h-100">
          <div
            class="row d-flex justify-content-center align-items-center h-100"
          >
            <div class="col-12 col-md-9 col-lg-7 col-xl-6">
              <div class="card" style="border-radius: 15px">
                <div class="card-body p-5">
                  <h2 class="text-uppercase text-center mb-5">
                    Isi Data Diri
                  </h2>

                  <form id="form-pengguna" @submit.prevent="onFormAddPengguna">
                    <input
                      id="id"
                      v-model="penggunaId"
                      name="id"
                      type="hidden"
                      class="form-control"
                    >
                    <div class="form-outline mb-4">
                      <input
                        id="username"
                        type="text"
                        class="form-control form-control-lg"
                      >
                      <label
                        class="form-label"
                        for="username"
                      >Input Your Username</label>
                    </div>
                    <div class="form-outline mb-4">
                      <input
                        id="email"
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
                        type="tel"
                        class="form-control form-control-lg"
                      >
                      <label
                        class="form-label"
                        for="no_hp"
                      >Input No Hp</label>
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
  methods: {
    async onFormAddPengguna () {
      //   const tambahProducts = document.getElementById('tambah-products')
      //   // eslint-disable-next-line no-use-before-define, new-cap
      //   const formData = new formData(tambahProducts)
      const dataForm = {
        // penggunaId: document.getElementById('id').value,
        username: document.getElementById('username').value,
        email: document.getElementById('email').value,
        password: document.getElementById('password').value,
        alamat: document.getElementById('alamat').value,
        no_hp: document.getElementById('no_hp').value
      }
      console.log(dataForm)
      const response = await fetch(
        'https://jylpaciooxarhelwslji.supabase.co/rest/v1/pengguna',
        {
          method: 'POST',
          headers: {
            apiKey:
              'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU',
            'Content-Type': 'application/json',
            Prefer: 'return=representation',
            some_column: 'someValue',
            other_column: 'otherValue'
          },
          body: JSON.stringify(dataForm)
        }
      )
      // console.log(await response?.json())
      const data = await response?.json()
      console.log(data)
      // this.$router.push(`/app/profile/${data[0]?.username}`)
      this.$router.push('/log-in')
    }
  }
}
</script>
<style scoped>

.gradient-custom-3 {
  background: #84fab0;

  background: -webkit-linear-gradient(
    to right,
    rgba(208, 208, 208, 0.5),
    rgba(218, 218, 218, 0.5)
  );

  background: linear-gradient(
    to right,
    rgba(255, 255, 255, 0.5),
    rgba(143, 211, 244, 0.5)
  );
}
.gradient-custom-4 {
  background: #17b6e2;

  background: -webkit-linear-gradient(
    to right,
    rgba(132, 250, 176, 1),
    rgba(143, 211, 244, 1)
  );

  background: linear-gradient(
    to right,
    rgb(60, 214, 155),
    rgb(47, 174, 238)
  );
}
</style>
