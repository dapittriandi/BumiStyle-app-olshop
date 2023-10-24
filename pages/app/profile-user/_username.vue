<template>
  <section class="vh-100" style="background-color: #eee; height: 100vh">
    <div class="container py-5 h-100">
      <div class="row d-flex justify-content-center align-items-center h-100">
        <div class="col-md-12 col-xl-4">
          <div class="card" style="border-radius: 15px; width: 700px">
            <div class="card-body text-center">
              <div class="mt-3 mb-4">
                <i
                  class="fa fa-user-circle rounded-circle img-fluid"
                  style="
                    font-size: 48px;
                    color: rgb(20, 159, 218);
                    width: 100px;
                  "
                />
              </div>
              <h4 class="mb-2">
                {{ username }}
              </h4>
              <p class="text-muted">
                No Hp<span class="mx-2">:</span>0{{ no_hp }}
                <i class="fa fa-phone" style="" />
              </p>
              <p class="text-muted" style="text-align: center">
                Alamat<span class="mx-2">:</span>{{ alamat }}
                <i class="fas fa-map-marker-alt" />
              </p>
              <p class="text-muted">
                Email<span class="mx-2">:</span>
                <a href="#!"><strong>{{ email }}</strong></a>
              </p>
              <button
                type="button"
                class="btn btn-primary btn-sm"
                style="border-radius: 10px"
                @click="onEdit"
              >
                Edit Profile!<i class="fa fa-edit" />
              </button>
              <button
                type="button"
                class="btn btn-danger btn-sm"
                style="border-radius: 10px; margin-left: 5px"
                @click="deleteDataProfile"
              >
                Hapus Profile!<i
                  class="fa fa-trash-o"
                  style="margin-left: 2px"
                />
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  layout (context) {
    return 'CustomDefault'
  },
  data () {
    return {
      penggunaId: '',
      username: '',
      email: '',
      alamat: '',
      no_hp: 0
    }
  },
  mounted () {
    // this.deleteDataProducts()
    const params = this.$route.params
    // eslint-disable-next-line quotes
    this.getProfile(params?.username)
  },
  methods: {
    async getProfile (username) {
      const response = await fetch(
        `https://jylpaciooxarhelwslji.supabase.co/rest/v1/pengguna?username=eq.${username}`,
        {
          headers: {
            apikey:
              'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU',
            'Content-Type': 'application/json'
          }
        }
      )
      const data = await response.json()
      console.log(data)
      this.username = data[0]?.username
      this.email = data[0]?.email
      this.password = data[0]?.password
      this.alamat = data[0]?.alamat
      this.no_hp = data[0]?.no_hp
      this.penggunaId = data[0]?.id
    },
    onEdit () {
      this.$router.push(`/app/form/${this.username}/edit-user`)
    },
    async deleteDataProfile () {
      await fetch(
        'https://jylpaciooxarhelwslji.supabase.co/rest/v1/pengguna?username=eq.' +
          this.username,
        {
          // eslint-disable-next-line quotes
          method: 'DELETE',
          headers: {
            apiKey:
              'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU'
          }
        }
      )
      this.$router.push('/')
    }
  }
}
</script>
<style scoped>
.card {
    position: relative;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: row;
    min-width: 0;
    word-wrap: break-word;
    background-color: #fff;
    background-clip: border-box;
    border: 1px solid rgba(0,0,0,.125);
    border-radius: .25rem;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    align-content: center;
}
</style>
