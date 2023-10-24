<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container">
      <a class="navbar-brand" href="/home">Bumi Style</a>
      <b-navbar-toggle target="nav-collapse" />
      <b-collapse id="nav-collapse" is-nav>
        <ul class="navbar-nav ml-auto" style="padding-left: 30PX;">
          <li class="nav-item">
            <a class="nav-link" href="/home">Home</a>
          </li>
          <li class="nav-item">
            <div class="navbar-item has-dropdown is-hoverable">
              <a
                class="navbar-link"
                style="
                  border-radius: 10px;
                  text-decoration: none;
                  font-family: 'Roboto Condensed', sans-serif;
                  color: #000;
                "
              >Product</a>
              <div class="navbar-dropdown">
                <nuxt-link class="navbar-item" to="/app/product">
                  View All Product
                </nuxt-link>
                <nuxt-link class="navbar-item" to="/app/form/add-product">
                  Add Product
                  <i
                    class="fa fa-plus"
                    style="font-size: 15px; color: #3877ff; margin-left: 2px"
                  />
                </nuxt-link>
              </div>
            </div>
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              href="/about"
            >About<i
              class="fa fa-exclamation-circle"
              style="margin-left: 3px; color: #3877ff; font-size: 18px"
            /></a>
          </li>
          <li>
            <div
              class="navbar-item has-dropdown is-hoverable"
              style="
              font-family: 'Roboto Condensed', sans-serif;
              color: #000;
            "
            >
              <a class="navbar-link" style="border-radius: 10px; color: #000">
                <i
                  class="fas fa-user"
                  style="color: #3877ff; font-size: 20px"
                /></a>
              <div class="navbar-dropdown">
                <nuxt-link class="navbar-item" to="/app/profile">
                  Profile Settings
                  <i
                    class="fa fa-gear"
                    style="color: #424d63; font-size: 15px"
                  />
                </nuxt-link>
                <hr class="navbar-divider">
              </div>
            </div>
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              @click="logout()"
            >
              <i
                class="fa fa-sign-out"
                style="font-size: 20px; color: brown;"
              />
            </a>
          </li>
        </ul>
      </b-collapse>
    </div>
  </nav>
</template>
<script>

export default {
  // eslint-disable-next-line vue/order-in-components
  head () {
    return {
      link: [
        { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' },
        {
          rel: 'stylesheet',
          href: 'https://fonts.googleapis.com/css?family=Roboto:300,400,500,700|Material+Icons'
        },
        {
          rel: 'stylesheet',
          href: 'https://fonts.googleapis.com/css?family=Roboto:300,400,500,700|Roboto+Slab:400,700|Material+Icons'
        },
        {
          rel: 'stylesheet',
          href: 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css'
        }
      ],
      scripts: [
        {
          src: 'https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js',
          body: true
        }
      ]
    }
  },

  methods: {
    logout () {
      this.$router.push('/')
    }
  }
}
</script>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: 'Merriweather Sans', sans-serif;
  padding: 10px 0;
  background-color: rgba(209, 209, 209, 0.305) !important;
  backdrop-filter: saturate(180%) blur(20px);
  -webkit-backdrop-filter: saturate(180%) blur(20px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.185);
  z-index: 999;
  position: sticky;
  /* opacity: 0.9; */
  top: 0;
  left: 0;
}

.navbar-brand {
  font-size: 21px;
  font-weight: 600;
  font-family: 'Merriweather Sans', sans-serif;
}

.nav-item {
  font-size: 16px;
  font-family: 'Roboto Condensed', sans-serif;
}

.navbar-light .nav-link {
  color: rgb(0, 0, 0);
  transition-duration: 0.3s;
}

.navbar-light .nav-link:hover {
  color: #3877ff;
}

.login {
  font-size: 16px;
  border-radius: 10px;
  outline: none;
  padding: 6px 13px;
  text-decoration: none;
  color: #000000;
  transition: 0.5s;
}

.register {
  color: #fff;
  background-color: #3877ff;
  font-size: 16px;
  border-radius: 10px;
  margin-left: 2px;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.359);
  padding: 7px 14px;
  text-decoration: none;
  transition: 0.5s;
}

.login:hover {
  background-color: transparent;
  border: 1px solid #000000;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.359);
  padding: 5px 12px;
}

.register:hover {
  background-color: transparent;
  color: #000000;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.359);
  border: 1px solid #000000;
  padding: 5px 12px;
}

@media (max-width: 799px) {
  .navbar {
    background-color: #e3e6f3;
  }
}
</style>
