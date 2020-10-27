<template>
  <button @click="lanzarEvento">{{ titulo }}</button>
</template>

<script>
export default {
  name: "BotonCuenta",
  props: {
    titulo: {
      type: String,
      default: "Soy un boton",
    },
  },
  methods:{
      lanzarEvento(){
          this.$emit("hicieronClick", 25)
      }
  }
};
</script>

<style scoped>
button{
  position: relative;
  padding: 10px;
  margin: 3px;
  border-radius: 15px;
  text-transform: uppercase;
  border: 1px solid #2196f3;
  background: transparent;
  color: #2196f3;
  outline: none;
  transition: 0.5s;
}
button:hover{
  color: #fff;
  background: #2196f3;
  box-shadow: 0 0 15px #2196f3, 0 0 40px #2196f3, 0 0 80px #2196f3;
}
button::before{
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 0%;
  height: 100%;
  border-radius: 15px;
  background: rgb(35, 170, 141);
  transition: 0.5s;
  opacity: 0.5;
}
button:hover::before{
  width: 100%;
}
button:disabled{
  background: rgb(112, 112, 112);
  color: #fff;
  border: 2px solid #fff;
}
button:disabled:hover{
  transform: rotateY(360deg);
  box-shadow: 0 0 15px rgb(112, 112, 112), 0 0 40px rgb(112, 112, 112), 0 0 80px rgb(112, 112, 112);
}
button:disabled:hover::before{
    width: 0;
}
</style>