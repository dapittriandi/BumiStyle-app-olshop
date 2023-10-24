<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container">
        <a class="navbar-brand" href="#!">Bumi Style</a>
        <b-navbar-toggle target="nav-collapse" />
        <b-collapse id="nav-collapse" is-nav />
      </div>
    </nav>
    <div class="containerMasuk">
      <section class="hero py-4">
        <h1
          style="
            text-align: center;
            color: #0f7f9b;
            font-weight: 800;
            font-style: italic;
          "
        >
          Bumi Style
        </h1>
        <div class="text-center">
          <h1 class="title mb-4" style="color: #2b2929">
            Ayo
            <span style="font-weight: bold; color: rgb(18, 96, 204)">Masuk</span>
            dulu
            <span style="font-weight: bold;">liat-liat</span>
            mana tau
            <span style="font-weight: bold; color: #1da5a5">tertarik.</span>
          </h1>
          <a href="/log-in" class="btn btn-primary masuk">Masuk <i class="fas fa-sign-in-alt" /></a>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  layout (context) {
    // return 'CustomDefault'
  }
}
</script>
<style scoped>
.containerMasuk {
  height: 83vh;
  width: 100%;
  margin-bottom: 0.1rem;
  /* background: #ebebebbb; */
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Roboto Condensed', sans-serif;
}

.masuk {
  padding: 5px 35px;
  border-radius: 15px;
  font-size: 20px;
  color: #fff;
  background-color: #1da5a5;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.359);
  outline: none;
  border: none;
}
.masuk:hover {
  padding: 5px 35px;
  opacity: 0.9;
  color: #000000;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.359);
  border: 1px solid #000000;
}

.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: 'Merriweather Sans', sans-serif;
  padding: 20px 0;
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
