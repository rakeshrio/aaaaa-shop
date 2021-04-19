<template>
  <div class="col-md-12 col-12  bg-white" >
      <div class="col-md-12 col-12" >
        <div class=" col-md-6 pt-5 text-center " style="margin: 0 auto">
          <img class="pt-5 m" src="../assets/bikex-thankyou.jpg" width="70%" height="auto" >
      </div>
      <h3 class="py-5 text-center" >We'll get back to you soon !!!</h3>
      </div>
  </div>
</template>

<script>
export default {
 created() {
    window.addEventListener('scroll', this.handleScroll);
    window.scrollTo({
      top: 0,
      left: 0,
      behavior: "smooth",
    });
}
}
</script>

<style scoped>

</style>