<template>
  <section class="features__container">
    <div class="container">
      <div class="cards">
        <article
          v-for="(card, idx) in cards"
          :key="idx"
          class="card"
          tabindex="0"
          :aria-label="card.title"
        >
          <div class="icon">
            <component :is="card.icon" />
          </div>

          <div class="card__body">
            <h3 class="card__title">{{ card.title }}</h3>
            <p class="card__desc">{{ card.desc }}</p>
          </div>
        </article>

      </div>
    </div>
  </section>
</template>

<script setup>
import { reactive } from 'vue';
import { Activity, Wind, ThumbsUp, Sprout, EqualApproximately, Eye} from "lucide-vue-next";

const cards = reactive([
  {
    title: 'Lightweight',
    desc: 'Feather-light construction for effortless steps during long days.',
    icon: Activity
  },
  {
    title: 'Breathable Mesh',
    desc: 'Advanced knit lets air circulate while maintaining structure.',
    icon: Wind
  },
  {
    title: 'Cushion Comfort',
    desc: 'Layered foam with responsive rebound for all-day comfort.',
    icon: ThumbsUp
  },
  {
    title: 'Eco Materials',
    desc: 'Recycled fabrics & low-impact dyes reduce environmental footprint.',
    icon: Sprout
  },
  {
    title: 'Durable Outsole',
    desc: 'Grip-focused rubber compound for reliable traction and wear life.',
    icon: EqualApproximately
  },
  {
    title: 'Ergonomic Fit',
    desc: 'Contoured last and adaptive lacing for secure, personalized fit.',
    icon: Eye
  }
]);
</script>

<style>
.features__container{
  padding: 4rem 1.25rem;
  background: #fff;
  color: #111827;
}
.container{
  max-width: 1100px;
  margin: 0 auto;
}

.cards{
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.25rem;
}

.card{
  display: flex;
  gap: 1rem;
  align-items: flex-start;
  padding: 1.15rem;
  border-radius: 12px;
  background: linear-gradient(180deg, #ffffff, #fbfdff);
  box-shadow: 0 6px 18px rgba(16,24,40,0.06);
  transition: all .3s ease;
  border: 1px solid rgba(15,23,42,0.03);
  cursor: pointer;
  outline: none;
}

.card:hover{
  transform: translateY(-8px);
  box-shadow: 0 18px 36px rgba(16,24,40,0.10);
}

.icon{
  width: 56px;
  height: 56px;
  flex: 0 0 56px;
  display:flex;
  align-items:center;
  justify-content:center;
  background: linear-gradient(180deg, rgba(118,75,162,0.08), rgba(102,126,234,0.04));
  border-radius: 10px;
  color: #4c51bf; 
}

.icon svg{
  width: 28px;
  height: 28px;
}

.card__title{
  margin: 0;
  font-size: 1rem;
  font-weight: 700;
}
.card__desc{
  margin-top: 0.35rem;
  margin-bottom: 0;
  color: #6b7280;
  font-size: .92rem;
}

@media (width<980px){
  .cards{ 
    grid-template-columns: repeat(2, 1fr); 
  }
}
@media (max-width: 580px){
  .cards{ 
    grid-template-columns: 1fr; 
  }

  .card{ 
    align-items:center; 
    text-align:center; 
    flex-direction: column; 
    gap: .75rem; 
    padding: 1rem; 
  }

  .icon{ 
    margin-top: 0.25rem; 
  }

  .card__body{ 
    width: 100%; 
  }
}
</style>
