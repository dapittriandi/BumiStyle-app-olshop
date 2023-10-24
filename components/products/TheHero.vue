<template>
  <div>
    <section id="hero">
      <h4>Trade-in-offer</h4>
      <h2>super value deals</h2>
      <h1>On all products</h1>
      <p>Save more with coupons & up to 70% off!</p>
      <button>Shop Now</button>
    </section>

    <section id="feature" class="section-p1">
      <div class="fe-box">
        <img src="~/assets/f1.png" alt="">
        <h6>Free Shipping</h6>
      </div>
      <div class="fe-box">
        <img src="~/assets/f2.png" alt="">
        <h6>Online Order</h6>
      </div>
      <div class="fe-box">
        <img src="~/assets/f3.png" alt="">
        <h6>Save Money</h6>
      </div>
      <div class="fe-box">
        <img src="~/assets/f4.png" alt="">
        <h6>Promotions</h6>
      </div>
      <div class="fe-box">
        <img src="~/assets/f5.png" alt="">
        <h6>Happy Sell</h6>
      </div>
      <div class="fe-box">
        <img src="~/assets/f6.png" alt="">
        <h6>F24/7 Support</h6>
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

/*homepage*/
#hero {
  background-image: url('~/assets/cloth6.png');
  height: 90vh;
  width: 100%;
  background-size: cover;
  background-position: top 25% right 0;
  padding:  0 80px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-items: center;
}

#hero h4 {
  margin-top: 150px;
  padding-bottom: 15px;
}
#hero h1 {
  color: #088178;
}
#hero button {
  background-image: url('~/assets/img/button.png');
  background-color: transparent;
  color: #088178;
  border: 0;
  padding: 14px 80px 14px 65px;
  background-repeat: no-repeat;
  background-position: center;
  cursor: pointer;
  font-weight: 700;
  font-size: 15px

}

#feature {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
}

#feature .fe-box {
width: 180px;
text-align: center;
padding: 25px 15px;
box-shadow: 20px 20px 34px rgba(0, 0, 0, 0.03);
border: 1px solid #cce7d0;
border-radius: 4px;
margin: 15px 0;
}

#feature .fe-box:hover {
  box-shadow: 10px 10px 54px rgba(0,0,0,0.01);
}

#feature .fe-box img {
  width: 100%;
  margin-bottom: 10px;
}

#feature .fe-box h6 {
  display: inline-block;
  padding: 9px 8px 6px 8px;
  line-height: 1;
  border-radius: 4px;
  color: #088178;
  background-color: #fdddfde4;
}

#feature .fe-box:nth-child(2) h6 {
  background-color: #cdebbc;

}

#feature .fe-box:nth-child(3) h6 {
  background-color: #d1e8f2;

}

#feature .fe-box:nth-child(4) h6 {
  background-color: #cdd4f8;

}

#feature .fe-box:nth-child(5) h6 {
  background-color: #f6dbf6;

}

#feature .fe-box:nth-child(6) h6 {
  background-color: #fff2e5;

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
  #feature {
    justify-content: space-between;
  }
  #feature .fe-box {
    width: 155px;
    margin: 0 0 15px 0;
  }
  #banner3 {
    padding: 0 20px;
  }
}
</style>
