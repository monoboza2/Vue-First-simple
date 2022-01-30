<template>
  <li>
        <img src="https://cdn-icons.flaticon.com/png/512/560/premium/560277.png?token=exp=1643541078~hmac=b2ff03fe4775b422b9ce7ee411ec7b98" />
        <hr>
        <slot name="card-header"></slot>
        <slot name="card-button"></slot>
        <slot name="card-content"></slot>
  </li>
</template>

<script>
export default {

}
</script>

<style scoped>
 li{
    margin:1rem 0;
    font-size:1.25rem;
    font-weight:bold;
    background:pink;
    padding:0.5rem;
    color:white;
    border-radius:25px;
  }
  img{
      width:200px;
      height:200px;
  }
</style>