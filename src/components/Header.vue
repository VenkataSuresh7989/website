<template>
  <div>
    <header class="header">
      <div class="container">
        <div class="row">
          <div class="col-5">
            <a class="logo">My Profile</a>
          </div>
          <div class="col-7">
            <nav class="navbar">
              <button class="btn navbar-toggle" id="toggleBtn" @click="toggleMenu">
                <span class="toggle-icon"></span>
              </button>
              <ul class="navbar-menu" id="navMenu">
                <li><a href="#">Home</a></li>
                <li><a href="#aboutUs">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#contactUs">Contact</a></li>
              </ul>
            </nav>
          </div>
        </div>
      </div>
    </header>
  </div>
</template>
<script>
export default {
  name: 'HeaderView',
  mounted() {
    this.toggleMenu();
    document.getElementById("toggleBtn").classList.remove("active");
    document.getElementById("navMenu").classList.remove("active");
  },
  methods: {
    toggleMenu: function () {
      document.getElementById("toggleBtn").classList.toggle("active");
      document.getElementById("navMenu").classList.toggle("active");
    },
  }

}
</script>