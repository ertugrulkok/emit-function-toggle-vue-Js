<template>
<li>
  <div class="container">
    <div class="card" style="width: 25rem; height: 33rem;">
  <img src="@/assets/camaro_0.png" class="card-img-top" alt="...">
  <div class="card-body">
    <h2 class="card-title">Model : {{modelCar}}</h2>
     <h2 class="card-title">Brand : {{brandCar}}</h2>
        <h2 class="card-title">Release Date : {{releasedateCar}}</h2>
        <br>
        <h5 style="color:red; font-size:">{{luxurylineCar ? "This car is a Luxury Line Series" : "This car is not a Luxury Line Series"}}</h5>
        


<br>
   <button type="button" @click="changeProperty" class="btn btn-success">Change Property</button>
  </div>
</div>
  </div>
  </li>
</template>

<script>


export default {
  name: 'HelloWorld',
  props: {
    id:String,
    imageUrl:String,
    modelCar:String,
    brandCar:String,
    releasedateCar:String,
    luxurylineCar:{
      type:Boolean,
      required:false,
      default:false
      
    }

  },
  methods:{
    changeProperty(){ 
      this.$emit('luxury-option', this.id);
  },
}
}

</script>



