<template>
  <div class="container" style="display:flex;justify-content: center; align-items: center;;">
    <div class="card mb-3 shadow p-3 mb-5 bg-body-tertiary rounded" style="width: 750px; margin-top:15px; ">
      <div class="row g-0">
        <div class="col-md-4">
          <img src="https://images.pexels.com/photos/18536062/pexels-photo-18536062/free-photo-of-potret-di-kota-tua.jpeg?auto=compress&cs=tinysrgb&w=400" class="img-fluid rounded-start" alt="...">
        </div>
        <div class="col-md-8">
          <div class="card-body">
            <h5 class="card-title text-center">
              About
            </h5>
            <p class="card-tex text-center">
              Website ini terinsiprasi dari style anak muda masa kini dan ketertarikan saya pada suatu product.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout (context) {
    return 'CustomDefault'
  }
}
</script>

<style scoped>
.container {
  height: 83vh;
  /* width: 100%;
  margin-bottom: 0.1rem;
  background-color: #9a616d;
  display: flex;
  align-items: center;
  justify-content: center; */
}
.rounded {
  border-radius: 20px;
}
</style>
