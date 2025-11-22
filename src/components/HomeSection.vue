<template>
  <section class="home__section">
    <div class="home__inner">
      <div class="text__area">
        <h2 class="logo__name">Breezes</h2>
        <h1 class="logo__header">Move Lightly.<br />Step Confidently.</h1>
        <p class="logo__description">
          Experience comfort and style with every step — engineered for movement, designed for you.
        </p>

        <div class="btns">
          <button class="btn primary">Shop Now</button>
          <button class="btn second">Learn More</button>
        </div>
      </div>

      <div class="image__area">
        <img :src="shoe" alt="Stylish Shoe" class="shoe" />
      </div>
    </div>
  </section>
</template>

<script setup>
import shoe from '../assets/shoe.png'

</script>

<style>

.home__section {
  position: relative;
  overflow: hidden;
  background: linear-gradient(180deg, #f8f9ff 0%, #ffffff 100%);
  padding: 6rem 1.5rem 5rem;
}

.home__inner {
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 2.5rem;
  flex-wrap: wrap;
  position: relative;
  z-index: 1;
}


.text__area {
  flex: 1 1 420px;
}

.logo__name {
  font-size: 1rem;
  font-weight: 700;
  color: #6b66e6;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-bottom: 0.5rem;
}

.logo__header {
  font-size: 2.3rem;
  font-weight: 800;
  color: #111827;
  line-height: 1.2;
  margin-bottom: 1rem;
}

.logo__description {
  font-size: 1rem;
  color: #6b7280;
  margin-bottom: 1.8rem;
  max-width: 420px;
}

.btns {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.btn {
  font-size: 0.95rem;
  padding: 0.75rem 1.6rem;
  border-radius: 9999px;
  border: none;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: 600;
  box-shadow: 0 4px 14px rgba(0,0,0,0.06);
}

.btn.primary {
  background: var(--primary-color);
  color: white;
}

.btn.primary:hover {
  box-shadow: 0 10px 20px rgba(102,126,234,0.25);
}

.btn.second {
  background: white;
  color: #374151;
  border: 1px solid #d1d5db;
}

.btn.second:hover {
  background: #f9fafb;
}

.image__area {
  flex: 1 1 400px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.shoe {
  width: 100%;
  max-width: 480px;
  height: auto;
  display: block;
  animation: shoe-float 4s ease-in-out infinite;
  filter: drop-shadow(0 12px 18px rgba(0,0,0,0.15));
  transition: transform 0.3s ease;
}

.shoe:hover {
  transform: translateY(-6px) scale(1.03);
}

@keyframes shoe-float {
  0% { 
    transform: translateY(0); 
  }

  50% { 
    transform: translateY(-14px); 
  }

  100% { 
    transform: translateY(0); 
  }
}

@media (width<880px) {
  .home__inner {
    flex-direction: column;
    text-align: center;
  }

  .text__area {
    flex: 1 1 100%;
  }

  .logo__header {
    font-size: 1.8rem;
  }

  .logo__desc {
    margin: 0 auto 1.8rem;
  }

  .btn__group {
    justify-content: center;
  }

  .btns{
    justify-content: center;
  }
}
</style>