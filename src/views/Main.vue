<template>
  <div class="main-container">
    <div>
      <h2>KㅓBㅣ의 가계부</h2>
      <nav>
        <ul class="menu-list">
          <li>My page</li>
          <li>거래 내역</li>
          <li>예산</li>
        </ul>
        <hr />
      </nav>
      <nav>
        <div class="button-style">
          <button type="button" class="button-reset">최근·전체·최신순</button>
          <button type="button" class="round-button">작성✏️</button>
        </div>
      </nav>
    </div>
    <div class="main-section">
      <nav>
        <ul class="category-style">
          <li>날짜</li>
          <li>카테고리</li>
          <li>수입/지출</li>
        </ul>
      </nav>
      <div class="main-section">
        <span>{{ currentDate }}</span>
      </div>
    </div>
    <footer>
      <p>footer</p>
      <router-link to="/">로그아웃</router-link>
    </footer>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainPage',
  setup() {
    const today = new Date()
    const currentDate = ref(
      `${today.getFullYear()}-${String(today.getMonth() + 1).padStart(2, '0')}-${String(today.getDate()).padStart(2, '0')}`,
    )

    return { currentDate }
  },
})
</script>

<style>
.main-container {
  text-align: center;
  margin: 20px;
  font-family: Arial, sans-serif;
}

.menu-list {
  list-style-type: none;
  padding: 0;
  margin: 0 auto;
  justify-content: center;
}

.menu-list li {
  display: inline-block;
  padding: 30px;
}
.category-style {
  list-style-type: none;
  padding: 0;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  gap: 100px;
  font-size: 10px;
}

.category-style li {
  display: inline-block;
  padding: 20px;
}

.button-style {
  display: flex;
  justify-content: center;
  gap: 300px;
  margin: 10px 0;
}

.button-reset {
  background: none;
  border: none;
  padding: 0;
  margin: 0;
  font: inherit;
  color: inherit;
  cursor: pointer;
  font-size: 5px;
}

.round-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 5px;
  background-color: #1a1a3a;
  color: white;
  border: none;
  border-radius: 50px;
  padding: 5px 8px;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
  outline: none;
  font-size: 5px;
}

.round-button:hover {
  background-color: #2b2b5c;
}
</style>
