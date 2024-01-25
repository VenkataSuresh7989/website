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
    components:{
      Header, Footer, MainBody
    }
  }
</script>
