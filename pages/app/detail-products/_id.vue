<template>
  <div style="height: 100vh;">
    <section class="h-100" style="background-color: #eee">
      <div class="container">
        <div class="col-lg-8 border p-3 main-section bg-white" style="border-radius: 10px;">
          <div class="row hedding m-0 pl-3 pt-0 pb-3">
            Detail Product
          </div>
          <div class="row m-0">
            <div class="col-lg-4 left-side-product-box pb-3">
              <img :src="gambar" class="border p-3">
              <span class="sub-img" />
            </div>
            <div class="col-lg-8">
              <div class="right-side-pro-detail border p-3 m-0">
                <div class="row">
                  <div class="col-lg-12">
                    <span>{{ brand }}</span>
                    <p class="m-0 p-0">
                      {{ kategori }}
                    </p>
                  </div>
                  <div class="col-lg-12">
                    <p class="m-0 p-0 price-pro">
                      Rp.{{ harga }}
                    </p>
                    <hr class="p-0 m-0">
                  </div>
                  <div class="col-lg-12 pt-2">
                    <h5>{{ title }}</h5>
                    <span>{{ deskripsi }}</span>
                    <hr class="m-0 pt-2 mt-2">
                  </div>
                  <div class="col-lg-12">
                    <p class="tag-section">
                      <strong>Size : {{ size }}</strong>
                    </p>
                    <p class="tag-section">
                      <strong>Stock : {{ stok }}</strong>
                    </p>
                  </div>
                  <div class="col-lg-12" />
                  <div class="col-lg-12 mt-3">
                    <div class="row">
                      <div class="col-lg-6 pb-2" style="color: #fff;">
                        <a class="btn btn-secondary w-100" @click="onEdit">Edit</a>
                      </div>
                      <div class="col-lg-6">
                        <nuxt-link :to="`/app/product`" style="color: #fff;">
                          <a class="btn btn-danger w-100" @click="deleteDataProducts">Delete<i class="fas fa-trash fa-lg" style="font-size: 15px;" /></a>
                        </nuxt-link>
                      </div>
                      <nuxt-link class="btn btn-primary btn-rounded btn-lg-3" to="/app/product">
                        View All Product
                      </nuxt-link>
                    </div>
                  </div>
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
      title: ' ',
      brand: ' ',
      harga: 0,
      gambar: ' ',
      size: '',
      stok: 0,
      kategori: '',
      productId: ''
    }
  },
  mounted () {
    this.deleteDataProducts()
    const params = this.$route.params
    // eslint-disable-next-line quotes
    this.getCartProduct(params?.id)
  },
  methods: {
    async getCartProduct (productId) {
      const response = await fetch(
        `https://jylpaciooxarhelwslji.supabase.co/rest/v1/products?id=eq.${productId}`,
        {
          headers: {
            apikey:
              'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU'
          }
        })
      const data = await response.json()
      console.log(data)
      this.title = data[0]?.title
      this.brand = data[0]?.brand
      this.gambar = data[0]?.gambar
      this.harga = data[0]?.harga
      this.productId = data[0]?.id
      this.deskripsi = data[0]?.deskripsi
      this.size = data[0]?.size
      this.stok = data[0]?.stok
      this.kategori = data[0]?.kategori
    },
    onEdit () {
      this.$router.push(`/app/form/${this.productId}/edit`)
    },
    async deleteDataProducts () {
      //   const tambahProducts = document.getElementById('tambah-products')
      //   // eslint-disable-next-line no-use-before-define, new-cap
      //   const formData = new formData(tambahProducts)
      // eslint-disable-next-line no-undef
      await fetch(
        'https://jylpaciooxarhelwslji.supabase.co/rest/v1/products?id=eq.' + this.productId,
        {
          // eslint-disable-next-line quotes
          method: 'DELETE',
          headers: {
            apiKey:
                'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp5bHBhY2lvb3hhcmhlbHdzbGppIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTU3MjIxODYsImV4cCI6MjAxMTI5ODE4Nn0.DxbkTiy25jW5QSd3FgEvZm2G21JzU9kbcBSCdkOvmrU'
            // eslint-disable-next-line quotes
            // 'Content-Type': 'application/json'
            // eslint-disable-next-line quotes
            // Prefer: 'return=representation'
          }
          // body: JSON.stringify(dataForm)
        }
      )
      // eslint-disable-next-line no-undef
      // refresh()
      // const data = await response?.json()
      // this.$router.push(`/app/cart/${data[0]?.id}`)
    }
  }
}

</script>

<style scoped>
body {
    font-family: 'Roboto Condensed', sans-serif;
    background-color: #f5f5f5
}

.hedding {
    font-size: 20px;
    color: #ab8181;
}
.main-section {
    position: absolute;
    left: 50%;
    right: 50%;
    transform: translate(-50%, 5%);
}

.left-side-product-box img {
    width: 100%;
}

.left-side-product-box .sub-img img {
    margin-top: 5px;
    width: 83px;
    height: 100px;
}

.right-side-pro-detail span {
    font-size: 15px;
}

.right-side-pro-detail p {
    font-size: 25px;
    color: #a1a1a1;
}

.right-side-pro-detail .price-pro {
    color: #E45641;
}

.right-side-pro-detail .tag-section {
    font-size: 18px;
    color: #5D4C46;
}

.pro-box-section .pro-box img {
    width: 100%;
    height: 200px;
}

@media (min-width:360px) and (max-width:640px) {
    .pro-box-section .pro-box img {
        height: auto;
    }
}
</style>
