<template>
  <section style="min-height: 100vh; font-size: Roboto;">
    <div class="container">
      <div class="justify-content-center align-items-center">
        <div v-for="(user, index) in pengguna" :key="index" class="card" style="border-radius: 15px;margin-top: 10px; " :user="user">
          <div class="card-body text-center">
            <div class="mt-3 mb-4">
              <i
                class="fa fa-user-circle rounded-circle img-fluid"
                style="
                    font-size: 60px;
                    color: rgb(20, 159, 218);
                    width: 100px;
                  "
              />
            </div>
            <h4 class="mb-2">
              {{ user.username }}
            </h4>
            <p class="text-muted">
              No Hp <span class="mx-2">:</span>0{{ user.no_hp }}<i class="fa fa-phone" style="margin-left: 2px;" />
            </p>
            <p class="text-muted">
              Alamat <span class="mx-2">:</span>{{ user.alamat }}<i class="fas fa-map-marker-alt" style="margin-left: 2px;" />
            </p>
            <p class="text-muted mb-4">
              Email<span class="mx-2">:</span> <a
                href="#!"
              ><strong>{{ user.email }}</strong></a>
            </p>
            <button type="button" class="btn btn-primary btn-sm" style="border-radius: 10px;" @click="onEdit">
              Edit Profile!<i class="fa fa-edit" style="margin-left: 2px;" />
            </button>
            <button type="button" class="btn btn-danger btn-sm" style="border-radius: 10px;margin-left: 5px;" @click="deleteDataProfile">
              Hapus Profile!<i
                class="fa fa-trash-o"
                style="margin-left: 2px;"
              />
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: 'ProfilePage',
  layout (context) {
    return 'CustomDefault'
  },
  data () {
    return {
      pengguna: []
    }
  },
  computed: {},
  mounted () {
    // console.log('user-profile: ', this.pengguna)
    // console.log('user-profile: ', this.data)
    this.getProfilePengguna()
  },
  methods: {
    async getProfilePengguna () {
      try {
        await this.$axios
          .$get('https://jylpaciooxarhelwslji.supabase.co/rest/v1/pengguna', {
            headers: {
              apikey:
                'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU'
            }
          })
          .then((res) => {
            res.map(data => this.pengguna.push(data))
          })
      } catch (e) {
        console.log(e)
      }
    },
    async deleteDataProfile () {
      try {
        await fetch(
          'https://jylpaciooxarhelwslji.supabase.co/rest/v1/pengguna?username=eq.' + this.pengguna[0]?.username,
          {
          // eslint-disable-next-line quotes
            method: 'DELETE',
            headers: {
              apiKey:
                'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU'
            }
          }
        )// this.$router.push('/')
      } catch (e) {
        console.log(e)
      }
    },
    onEdit () {
      // const username = this.pengguna?.username
      console.log(this.pengguna[0]?.username)
      this.$router.push(`/app/form/${this.pengguna[0]?.username}/edit-user`)
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
