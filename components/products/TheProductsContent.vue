<template>
  <div>
    <section id="sm-banner" class="section-p1" style="margin-top: 40px;">
      <div class="banner-box">
        <h4>crazy deals</h4>
        <h2>buy 1 get 1</h2>
        <span>the best classic dress is on sale at cara</span>
        <button class="white">
          Learn More
        </button>
      </div>
      <div class="banner-box banner-box2">
        <h4>spring/summer</h4>
        <h2>upcoming season</h2>
        <span>the best classic dress is on sale at cara</span>
        <button class="white">
          Collection
        </button>
      </div>
    </section>

    <section id="banner3">
      <div class="banner-box">
        <h2>SEASONAL SALE</h2>
        <h3>Winter Collection -50% OFF</h3>
      </div>
      <div class="banner-box banner-box2">
        <h2>NEW FOOTWEAR COLLECTION</h2>
        <h3>Spring / Summer 2022</h3>
      </div>
      <div class="banner-box banner-box3">
        <h2>T-SHIRTS</h2>
        <h3>New Trendy Prints</h3>
      </div>
    </section>

    <section id="newsletter" class="section-p1 section-m1">
      <div class="newstext">
        <h4>Sign Up For Newsletters</h4>
        <p>Get E-mail updates about our latest shop and <span>special offers.</span></p>
      </div>
      <div class="form">
        <input type="text" placeholder="Your email address">
        <button class="normal">
          Sign Up
        </button>
      </div>
    </section>
  </div>
</template>
<script>
export default {
  head () {
    return {
      link: [
        { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' },
        {
          rel: 'stylesheet',
          href: 'https://fonts.googleapis.com/css2?family=Spartan:wght@100;200;300;400;500;600;700;800;900&display=swap'
        }
      ]
    }
  }
}
</script>
<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Spartan", sans-serif;
}

html {
  scroll-behavior: smooth;
}

/* Global Styles */

h1 {
  font-size: 50px;
  line-height: 64px;
  color: #222;
}

h2 {
  font-size: 46px;
  line-height: 54px;
  color: #222;
}

h4 {
  font-size: 20px;
  color: #222;
}

h6 {
  font-weight: 700;
  font-size: 12px;
}

p {
  font-size: 16px;
  color: #465b52;
  margin: 15px 0 20px 0;
}

.section-p1 {
  padding: 40px 80px;
}

.section-m1 {
  margin: 40px 0;
}

button.normal {
font-size: 14px;
font-weight: 600;
padding: 15px 30px;
color: #000;
background-color: #fff;
border-radius: 4px;
cursor: pointer;
border: none;
outline: none;
transition: 0.2s;
}

button.white {
  font-size: 13px;
  font-weight: 600;
  padding: 11px 18px;
  color: #fff;
  background-color: transparent;
  border-radius: 4px;
  cursor: pointer;
  border: 1px solid #fff;
  outline: none;
  transition: 0.2s;
  }

body {
  width: 100%;
}

/*homepage*/

#product1 {
  text-align: center;

}

#banner {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  background-image: url("~/assets/banner/b2.jpg");
  width: 100%;
  height: 40vh;
  background-size: cover;
  background-position: center;
}

#banner h4 {
  color: #fff;
  font-size: 16px;

}

#banner h2 {
  color: #fff;
  font-size: 30px;
  padding: 10px 0;
}

#banner h2 span {
  color: #ef3636;

}

#banner button:hover {
  background-color: #008178;
  color: #fff;
}

/* #sm-banner {
  display: flex;
  justify-content: space-between;
} */

#sm-banner .banner-box{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  background-image: url("~/assets/banner/b17.jpg");
  min-width: 580px;
  height: 50vh;
  background-size: cover;
  background-position: center;
  padding: 30px;
}

#sm-banner .banner-box2 {
  background-image: url("~/assets/banner/b10.jpg");
}

#sm-banner h4 {
  color: #fff;
  font-size: 20px;
  font-weight: 300;
}

#sm-banner h2 {
  color: #fff;
  font-size: 28px;
  font-weight: 800;
}

#sm-banner span {
  color: #fff;
  font-size: 14px;
  font-weight: 500;
  padding-bottom: 15px;
}

#sm-banner .banner-box:hover button {
  background-color: #088178;
  border: 1px solid #088178;
}

#banner3 {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  padding: 0 80px;
}

#banner3 .banner-box{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  background-image: url("~/assets/banner/b7.jpg");
  min-width: 30%;
  height: 30vh;
  background-size: cover;
  background-position: center;
  padding: 20px;
  margin-bottom: 20px;
}

#banner3 .banner-box2{
  background-image: url("~/assets/banner/b4.jpg");
}

#banner3 .banner-box3{
  background-image: url("~/assets/banner/b18.jpg");
}

#banner3 h2 {
  color: #fff;
  font-weight: 900;
  font-size: 22px;
}

#banner3 h3 {
  color: #ec544e;
  font-weight: 800;
  font-size: 15px;
}

#newsletter{
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  align-items: center;
  background-image: url("~/assets/banner/b14.png");
  background-repeat: no-repeat;
  background-position: 20% 30%;
  background-color: #041e42;
}

#newsletter h4{
  font-size: 22px;
  font-weight: 700;
  color: #fff;
}

#newsletter p{
  font-size: 14px;
  font-weight: 600;
  color: #818ea0;
}

#newsletter p span {
  color: #ffbd27;
}

#newsletter .form {
  display: flex;
  width: 40%;
}

#newsletter input{
  height: 3.125rem;
  padding: 0 1.25rem;
  font-size: 14px;
  width: 100%;
  border: 1px solid transparent;
  border-radius: 4px;
  outline: none;
  border-top-right-radius: 0;
  border-bottom-right-radius: 0;
}

#newsletter button {
  background-color: #088178;
  color: #fff;
  white-space: nowrap;
  border-top-left-radius: 0;
  border-bottom-left-radius: 0;
}

/* Start media query */

@media (max-width:799px) {
  .section-p1 {
    padding: 40px 40px;
  }

  #hero {
    height: 70vh;
    padding: 0 80px;
    background-position: top 30% right 30%;
  }

  #feature {
    justify-content: center;
  }

}
#banner {
  height: 20vh;
}

#sm-banner {
  flex-wrap: wrap;
}

#sm-banner .banner-box {
  min-width: 100%;
  height: 50vh;
}

#banner3 {
  padding: 0 40px;
}

#banner3 .banner-box {
width: 28%;
}

#newsletter .form {
  width: 70%;
}

@media (max-width: 477px) {
  .section-p1 {
    padding: 20px;
  }
  h1 {
    font-size: 38px;
  }

  h2 {
    font-size: 32px;
  }

  #hero {
    padding: 0 20px;
    background-position: 55%;
  }
  #banner {
    height: 40vh;
  }
  #sm-banner .banner-box {
    height: 40vh;
  }
  #sm-banner .banner-box2 {
    margin-top: 20px;
  }
  #banner3 {
    padding: 0 20px;
  }
  #banner3 .banner-box {
    width: 100%;
  }
  #newsletter {
    padding: 40px 20px;
  }
  #newsletter .form {
    width: 100%;
  }
}
</style>
