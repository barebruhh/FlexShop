<template>
  <div class="app-root">
    <SiteHeader />

    <main class="seller-canvas" role="main" aria-label="Страница продавца">
      <div class="products-section">
        <div class="products-header">
          <h2 class="products-title">Товары</h2>
          <span class="products-count">шт.</span>
          <button class="add-product-btn" aria-label="Добавить товар">Добавить товар</button>
        </div>

        <div class="products-container">
          <!-- Здесь будут товары -->
        </div>
      </div>
    </main>

    <Footer />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import SiteHeader from '../components/Header.vue'
import Footer from '../components/Footer.vue'
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat+Alternates:wght@400;600&display=swap');
html,body,#app{height:100%;margin:0}
body{font-family:Inter, system-ui, Arial, sans-serif;background:#F5F5F5}

.app-root{min-height:100vh;display:flex;flex-direction:column;align-items:center}

.seller-canvas{max-width:1920px;width:100%;min-height:calc(100vh - 164px);background:#F5F5F5;padding:40px 64px;box-sizing:border-box}

.products-section{width:100%;background:#FFFFFF;border-radius:30px;padding:30px;box-sizing:border-box}

.products-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:20px;padding-bottom:16px;border-bottom:1px solid #E0E0E0;gap:20px}

.products-title{font-family:'Montserrat Alternates', sans-serif;font-size:32px;margin:0;color:#111;font-weight:600}

.products-count{font-size:16px;color:#666;font-family:'Montserrat Alternates', sans-serif}

.add-product-btn{background:#52C41A;color:#FFFFFF;border:none;border-radius:30px;padding:12px 30px;font-size:16px;font-family:'Montserrat Alternates', sans-serif;font-weight:600;cursor:pointer;box-shadow:0 6px 16px rgba(82, 196, 26, 0.25);transition:all 0.3s ease;margin-left:auto}

.add-product-btn:hover{background:#45A517;box-shadow:0 8px 20px rgba(82, 196, 26, 0.35)}

.add-product-btn:active{transform:scale(0.98)}

.products-container{display:flex;flex-direction:row;gap:20px;flex-wrap:wrap;min-height:200px;align-items:flex-start;justify-content:flex-start;color:#999;padding-top:20px}

@media (max-width:768px){
  .seller-canvas{padding:20px 16px}
  .products-section{padding:20px}
  .products-header{flex-direction:column;gap:15px;align-items:flex-start}
  .add-product-btn{width:100%}
  .products-title{font-size:24px}
}
</style>
