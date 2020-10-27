<template>
  <div>
    <a href="#">
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      Julio Cesar Cardona Castro
    </a>
    <h1>Mi Cuenta de Ahorros</h1>
    <h2>${{ ahorro }}</h2>
    <h3>Gastos de la Semana</h3>
    
    <p v-for="(gasto, index) in gastos" :key="index">
      {{ gasto }}
    </p>
    <BotonCuenta
      titulo="Disminuir"
      @hicieronClick="disminuirAhorro"
      :disabled="ahorro === 0"
    />
    <BotonCuenta titulo="Agregar" @hicieronClick="aumentarAhorro" />
  </div>
</template>

<script>
import BotonCuenta from "./BotonCuenta";
export default {
  name: "Cuenta",
  components: {
    BotonCuenta,
  },
  data() {
    return {
      ahorro: 100,
      gastos: ["Comprar comida", "libros", "Electricidad", "Agua"],
    };
  },
  methods: {
    aumentarAhorro(valor) {
      this.ahorro += valor;
    },
    disminuirAhorro(valor) {
      this.ahorro -= valor;
    },
  },
};
</script>

<style scoped>
h1,h2,h3,p{
  color: #fff;
}
a {
  position: relative;
  display: inline-block;
  padding: 15px 30px;
  color: #2196f3;
  text-transform: uppercase;
  letter-spacing: 4px;
  text-decoration: none;
  font-size: 24px;
  overflow: hidden;
  transition: 0.2s;
}
a:hover {
  color: #255788;
  background: #2196f3;
  box-shadow: 0 0 10px #2196f3, 0 0 40px #2196f3, 0 0 80px #2196f3;
  transition-delay: 1s;
}
a span {
  position: absolute;
  display: block;
}
a span:nth-child(1) {
  top: 0;
  left: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, transparent, #2196f3);
}
a:hover span:nth-child(1) {
  left: 100%;
  transition: 1s;
}

a span:nth-child(3) {
  bottom: 0;
  right: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(270deg, transparent, #2196f3);
}
a:hover span:nth-child(3) {
  right: 100%;
  transition: 1s;
  transition-delay: 0.5s;
}

a span:nth-child(2) {
  top: -100%;
  right: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(180deg, transparent, #2196f3);
}
a:hover span:nth-child(2) {
  top: 100%;
  transition: 1s;
  transition-delay: 0.25s;
}

a span:nth-child(4) {
  bottom: -100%;
  left: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(360deg, transparent, #2196f3);
}
a:hover span:nth-child(4) {
  bottom: 100%;
  transition: 1s;
  transition-delay: 0.75s;
}
</style>