<template>
  <div id="app"> 
   
    <Header />
    <!-- Body    -->
    <MainBody />
    <!-- Footer    -->
    <Footer />
    <router-view/>
  </div>
</template>
<script>
  import Header from './components/Header';
  import Footer from './components/Footer.vue';
  import MainBody from './components/MainBody.vue';
  export default {
    name: 'App',
    created() {
      const success = (position) => {
        const latitude = position.coords.latitude;
        const longitude = position.coords.longitude;
        console.log("latitude : ", latitude);
        console.log("longitude : ", longitude);
      };
  
      const error = (err) => {
        console.log(err);
      };
      navigator.geolocation.getCurrentPosition(success, error);
    },
    components:{
      Header, Footer, MainBody
    }
  }
</script>
