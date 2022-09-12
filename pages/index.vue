<template>
  <div class="main-container">
    <div style="width:300px;text-align: justify;">
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. In, consequuntur. Maiores, quae earum! Mollitia porro incidunt iste atque, doloremque consequuntur, quam maiores eligendi numquam sapiente excepturi a, qui dicta aperiam!
      <br/>
      <br/>
      <div style="text-align: center;">
        <v-btn style="primary">Menú</v-btn>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>
<style scoped>
.main-container{
  height:100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('assets/Coffee.jpg');
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
