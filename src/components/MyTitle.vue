<template>
  <header class="ms_header">
    <nav class="nav-bar">

      <div class="title">To Do List</div>
      
      <div class="container-img">
        <div class="col-5 fs-4 text-center icon">&star;</div>
        <div class="col-5 user-img text-center"><img src="../assets/user-image.jpeg" alt=""></div>
      </div>

    </nav>
  </header>
</template>

<script>
export default {
  name: 'MyTitle',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

/* header */
header{
  box-shadow: 0 15px 15px 0 rgb(0, 0, 0, 0.3);
  position: sticky;
  top: 0;
  z-index: 999;
}

.nav-bar{
  height: 12vh;
  justify-content: space-between;
  align-items: center;
  max-width: 1320px;
  margin: 0 auto;
  display: flex;
}

.title{
  flex: 0 0 auto;
  width: auto;
  font-size: 30px;
}

.container-img{
  flex: 0 0 auto;
  width: 16.6%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.icon{
  flex: 0 0 auto;
  width: 41.6%;
  font-size: 30px;
  font-weight: 600;
  text-align: center;
  color: rgb(255, 208, 0);
}

.user-img{
  flex: 0 0 auto;
  width: 41.6%;
  text-align: center;
}

.user-img > img{
  width: 40px;
  height: 40px;
  object-position: center;
  object-fit: cover;
  border-radius: 50%;
}
</style>
