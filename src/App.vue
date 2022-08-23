<template>
  <div class="container">
    <hello-world
      v-for="car in carBrands"
      :key="car.id"
      :id="car.id"
      :image-url="car.image"
      :model-car="car.model"
      :brand-car="car.brand"
      :releasedate-car="car.releaseDate"
      :luxuryline-car="car.luxuryLine"
      @luxury-option="getCarProperty"
    ></hello-world>
  </div>
</template>

<script>
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  data() {
    return {
      carBrands: [
        {
          id: "acura",
          image: "@/assets/acura_0.png",
          model: "MDX",
          brand: "ACURA",
          releaseDate: "2015",
          price: "100,000 €",
          luxuryLine: false,
        },
        {
          id:"chv" ,
          image: "@/assets/camaro_0.png",
          model: "CZ28 SS",
          brand: "CHEVROLET",
          releaseDate: "1998",
          price: "155,000 €",
          luxuryLine: false,
        },
        {
          id: "lnd",
          image: "src/assets/land_rover_0.png",
          model: "DISCOVERY",
          brand: "LAND ROVER",
          releaseDate: "2000",
          price: "185,000 €",
          luxuryLine: true,
        },
      ],
    };
  },
  methods: {
    getCarProperty(luxurycar) {
      const foundCar = this.carBrands.find(car => car.id == luxurycar);
    
      foundCar.luxuryLine = !foundCar.luxuryLine;
    
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Baloo+Bhai+2:wght@600&display=swap');
body {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: nowrap;
  min-height: 100vh;
  background: #232427;
   font-family: 'Baloo Bhai 2', cursive;
}

body .container {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  flex-wrap: nowrap;
  max-width: 1200px;
  margin: 40px 0;
  gap: 5rem;
}
</style>
