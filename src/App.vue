<template>
  <div id="app">
    <header class="header__container">
      <div class="navbar">
        <div class="logo">Breezes</div>
        <nav class="nav">
          <a href="#home">Home</a>
          <a href="#features">Features</a>
          <a href="#contact">Contact</a>
        </nav>
      </div>
    </header>
    <main>
      <HomeSection id="home" />
      <FeaturesSection id="features" />
    </main>
    <FooterSection />
  </div>
</template>

<script setup>
import HomeSection from './components/HomeSection.vue';
import FeaturesSection from './components/FeaturesSection.vue';
import FooterSection from './components/FooterSection.vue';
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Parkinsans:wght@300..800&display=swap');

:root{
  --max-width: 1100px;
  --primary-color: #6b66e6;
}

*{
  box-sizing: border-box

}

html,body,#app{
  height:100%
}

body{
  margin:0;
  padding: 0;
  font-family: "Parkinsans", sans-serif;
  background: #ffffff;
  color: #0f172a;
  line-height:1.4;
}

.header__container{
  z-index: 30;
  backdrop-filter: blur(6px);
  background: transparent;
  position: absolute;
  width: 100%;
  border-bottom: 1px solid rgba(15,23,42,0.03);
}

.navbar{
  max-width: var(--max-width);
  margin: 0 auto;
  padding: .7rem 1.25rem;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.logo{ 
  font-weight: 700; 
  letter-spacing: .02em; 
}

.nav a{
  margin-left: 1.15rem;
  color: #374151;
  text-decoration: none;
  font-weight: 600;
  font-size: .95rem;
  opacity:.95;
}
.nav a:hover{
  color: var(--primary-color); 
  transform: translateY(-2px); 
  transition: transform .16s, color .16s; 
}

@media (width<600px){
  
  .logo{ 
    font-size: 1rem; 
  }
}
</style>

