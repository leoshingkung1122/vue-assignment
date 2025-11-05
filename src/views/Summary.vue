<template>
  <div class="page-container">
    <h2>📋 Summary</h2>
    <!-- TODO: ดึง username และ favorites.length จาก store -->
    <template v-if="favoriteStore.username || favoriteStore.favorites.length > 0">
      <p>ชื่อผู้ใช้: {{ favoriteStore.username || '-' }}</p>
      <p>จำนวนคอร์สที่ถูกใจ: {{ favoriteStore.favorites.length }}</p>
    </template>
    <template v-else>
      <p>No course selection data available.</p>
    </template>
    <RouterLink to="/" class="back-link">Back to Course Page</RouterLink>
  </div>
</template>

<script setup>
// TODO: import { useFavoriteStore }
import { useFavoriteStore } from '../stores/favorite';
import { RouterLink } from 'vue-router';

const favoriteStore = useFavoriteStore();
</script>

<style scoped>
.page-container {
  text-align: center;
  padding: 40px;
}

.back-link {
  display: inline-block;
  margin-top: 20px;
  color: #42b883;
  text-decoration: none;
}

.back-link:hover {
  text-decoration: underline;
}
</style>
