<template>
  <div class="game-editor">
    <div class="left-section">
      <div class="photo-upload">
        <div class="photo-placeholder">+</div>
      </div>

      <p class="photo-label">Фото карточки товара</p>
    </div>

    <div class="center-section">
      <div class="product-image-wrapper">
        <img :src="game.image || ''" :alt="game.title || ''" class="product-image" />
        <button class="image-add-btn">+</button>
      </div>

      <div class="seller-note-box">
        <p class="seller-note">Примечание для продавцов: Выставляя товар, вы обязаны заполнить все поля товара, в противном случае ваш товар будет удален!</p>
      </div>

      <div class="product-description-box">
        <p class="product-description">Описание:</p>
      </div>

      <div class="price-section">
        <span class="price">Цена Руб.</span>
      </div>
    </div>

    <div class="right-section">
      <h1 class="product-title">Название</h1>

      <div class="seller-info">
        <img src="/src/assets/icons/saleman.svg" alt="Продавец" class="seller-icon" />
        <span class="seller-name">Dexter</span>
      </div>

      <div class="specs">
        <div class="spec-row">
          <span class="spec-label">Год выхода:</span>
        </div>
        <div class="spec-row">
          <span class="spec-label">Жанр:</span>
        </div>
        <div class="spec-row">
          <span class="spec-label">Разработчик:</span>
        </div>
        <div class="spec-row">
          <span class="spec-label">Версия:</span>
        </div>
        <div class="spec-row">
          <span class="spec-label">Язык интерфейса:</span>
        </div>
      </div>

      <div class="buttons-section">
        <button class="btn btn-save">Сохранить</button>
        <button class="btn btn-cancel">Отменить</button>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  game: {
    type: Object,
    default: () => ({})
  }
})
</script>

<style scoped>
.game-editor {
  width: 1505px;
  height: 865px;
  background: #EFEFEF;
  border: 8px solid #A53DFF;
  border-radius: 30px;
  display: flex;
  gap: 30px;
  padding: 30px;
  box-sizing: border-box;
  font-family: 'Montserrat Alternates', sans-serif;
}

.left-section {
  flex: 0 0 280px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.photo-upload {
  width: 280px;
  height: 305px;
  background: #E6E6E6;
  border-radius: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.3s ease;
}

.photo-upload:hover {
  background: #D9D9D9;
}

.photo-placeholder {
  font-size: 48px;
  color: #A53DFF;
  font-weight: 700;
}

.photo-label {
  margin: 0;
  font-size: 16px;
  color: #666;
  text-align: center;
  font-family: Inter, system-ui, Arial, sans-serif;
}

.center-section {
  flex: 0 0 612px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.product-image-wrapper {
  width: 612px;
  height: 428px;
  background: #E6E6E6;
  border-radius: 30px;
  overflow: hidden;
  position: relative;
}

.product-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.image-add-btn {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 60px;
  height: 60px;
  background: transparent;
  border: none;
  border-radius: 30px;
  color: #A53DFF;
  font-size: 48px;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 2;
}

.image-add-btn:hover {
  color: #A53DFF;
}

.seller-note-box {
  width: 612px;
  min-height: -60px;
  margin: 12px;
}

.seller-note {
  margin: 0;
  font-size: 12px;
  color: #666;
  line-height: 1.3;
  font-family: 'Montserrat Alternates', sans-serif;
  font-weight: 400;
}

.product-description-box {
  width: 612px;
  height: 115px;
  background: #E6E6E6;
  border-radius: 20px;
  padding: 16px;
  box-sizing: border-box;
  overflow: hidden;
}

.product-description {
  margin: 0;
  font-size: 20px;
  color: #666;
  line-height: 1.4;
  font-family: 'Montserrat Alternates', sans-serif;
}

.price-section {
  background: #E6E6E6;
  padding: 20px;
  border-radius: 30px;
  width: fit-content;
}

.price {
  font-size: 64px;
  color: #A53DFF;
  font-weight: 700;
  font-family: 'Montserrat Alternates', sans-serif;
}

.right-section {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.product-title {
  margin: 0;
  font-size: 36px;
  background: #E6E6E6;
  padding: 20px;
  border-radius: 30px;
  color: #111;
  font-weight: 600;
  line-height: 1.3;
  word-break: break-word;
  text-align: center;
}

.seller-info {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 12px 0;
  margin-top: -15px;
}

.seller-icon {
  width: 21px;
  height: 21px;
  flex-shrink: 0;
}

.seller-name {
  font-size: 24px;
  color: #454545;
  font-weight: 500;
}

.specs {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 14px;
  padding: 20px;
  background: #E6E6E6;
  border-radius: 30px;
}

.spec-row {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 20px;
  font-size: 24px;
  font-family: 'Montserrat Alternates', sans-serif;
}

.spec-label {
  color: #666;
  flex-shrink: 0;
  font-weight: 500;
}

.buttons-section {
  display: flex;
  flex-direction: column;
  gap: 16px;
  margin-top: auto;
  align-items: center;
}

.btn {
  width: 435px;
  height: 80px;
  border: none;
  border-radius: 30px;
  font-size: 32px;
  font-family: 'Montserrat Alternates', sans-serif;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}

.btn-save {
  background: #A53DFF;
  color: #FFFFFF;
  box-shadow: 0 8px 20px rgba(165, 61, 255, 0.25);
}

.btn-save:hover {
  background: #8B1FD9;
  box-shadow: 0 10px 28px rgba(165, 61, 255, 0.35);
}

.btn-save:active {
  transform: scale(0.98);
}

.btn-cancel {
  background: #0962C9;
  color: #FFFFFF;
  box-shadow: 0 8px 20px rgba(9, 98, 201, 0.25);
}

.btn-cancel:hover {
  background: #0751A3;
  box-shadow: 0 10px 28px rgba(9, 98, 201, 0.35);
}

.btn-cancel:active {
  transform: scale(0.98);
}


</style>
