<script>
import ComponenteTarea from './components/ComponenteTarea.vue';
export default {
  components: {
    ComponenteTarea
  },
 //data() {
   // return {
     // tareaNueva: "",
      //tareaPendiente: "",
      //tareaFinalizada: ""
    //}
 // }
}
</script>

<template>

  <div class="wrapper" id="root">
    <div class="box">
      <ComponenteTarea></ComponenteTarea>
      <!--<ComponenteTarea :llamar="valores"></ComponenteTarea>-->
    </div>
  </div>

</template>

<style scoped>
.wrapper {
  display: grid;
  justify-content: center;
  align-items: center;
  height: 50%;
  margin-top: 280px;
  width: 100%;

}

.box {
  background-color: rgb(211, 210, 206);
  width: 800px;
  height: 380px;
  justify-content: center;
  align-items: center;
  display: grid;
  border-radius: 10px;
  box-shadow: 10px 10px 15px 2px rgba(97, 92, 92, 0.671);
}
</style>
