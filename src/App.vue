<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header>


<nav class="navbar navbar-expand-lg bg-body-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">
      <img src="../src/assets/logo-3.png" alt="Logo"  class="" style="height: auto;max-width: 100%;width:130px;">
    </a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse " id="navbarNav">
      <ul class="navbar-nav  ms-auto mb-2 mb-lg-0 ">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Become Tutor <span class="tu-tag tu-bggreen">FREE</span></a>
        </li>
        <li class="nav-item">
          <a class="nav-link active" href="#">Signup As Student</a>
        </li>
        <li class="nav-item">
          <a class="nav-link active" href="#">Know More</a>
        </li>
        
    
      </ul>
    </div>
  </div>
</nav>
  </header>
  <body>
    <RouterView />
    <div class="container-fluid" style="background-color: #602eaf;color: white;">
  <footer class="py-5 p-5">
    <div class="row ">
      <h5 class="mb-4">Useful links</h5>
      
      <div class="col-6 col-md-2 mb-3">
        <ul class="nav flex-column">
          <li class="nav-item mb-2"><a href="#" class="nav-link p-0">.  Privacy Policy</a></li>
          <li class="nav-item mb-2"><a href="#" class="nav-link p-0 ">.  Tutor Signup</a></li>
      
        </ul>
      </div>

      <div class="col-6 col-md-2 mb-3">
     
        <ul class="nav flex-column ">
          <li class="nav-item mb-2"><a href="#" class="nav-link p-0 ">.  Top FAQ</a></li>
          <li class="nav-item mb-2"><a href="#" class="nav-link p-0 ">.  Tutor Login</a></li>
          
        </ul>
      </div>

      <div class="col-6 col-md-2 mb-3">
    
        <ul class="nav flex-column">
          <li class="nav-item mb-2"><a href="#" class="nav-link p-0 ">.  Legal Policies</a></li>
          <li class="nav-item mb-2"><a href="#" class="nav-link p-0 ">.  Student Signup</a></li>
         
        </ul>
      </div>
      <div class="col-6 col-md-2 mb-3">
    
    <ul class="nav flex-column">
      <li class="nav-item mb-2"><a href="#" class="nav-link p-0 ">.  TERMS OF USE</a></li>
      <li class="nav-item mb-2"><a href="#" class="nav-link p-0 ">.  Student login</a></li>
     
    </ul>
  </div>
      <div class="col-md-3 offset-md-1 mb-3">
        <form>
          <h5>Signup for newsletter</h5>
          <p>Corrupti quolores etmquasa molestias epturite sinteam occaecati amet cupiditate mikume molareshe.</p>
          <div class="d-flex flex-column flex-sm-row w-100 gap-2">
            <label for="newsletter1" class="visually-hidden">Email address</label>
            <input id="newsletter1" type="text" class="form-control" placeholder="Email address">
            <button class="btn btn-outline-secondary" type="button"><i class="fa-regular fa-paper-plane"></i></button>
          </div>
        </form>
      </div>

    </div>
     <div class="d-flex flex-column flex-sm-row justify-content-between  mt-5">
      <p>© 2022 - 2023 All Rights Reserved.</p>
      <ul class="list-unstyled d-flex">
        <li class="ms-3"><a class="nav-link" href="#">Privacy Policy</a></li>
        <li class="ms-3"><a class="nav-link" href="#">Top FAQ</a></li>
        <li class="ms-3"><a class="nav-link" href="#">Legal Policies</a></li>
        <li class="ms-3"><a class="nav-link" href="#">TERMS OF USE</a></li>
      </ul>
    </div>
  </footer>
</div>
  </body>


</template>

<style scoped>
body{
  font-family: 'Helvetica', 
}
.tu-login-left {
 
    width: 50%;
    display: flex;
    padding: 50px 30px;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    background-color: #0A0F26;
}
.tu-login-left_title h2 {
    margin-bottom: 0;
    color: #ffffff;
    font-weight: 600;
}
.nav-link {
  color: #ffffff;
}
</style>

<!-- <style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style> -->
