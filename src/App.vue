<template>
  <div>
    <!-- Judul -->
    <h1>{{ title }}</h1>

    <!-- Deskripsi -->
    <p>{{ description }}</p>

    <!-- Daftar makanan -->
    <h2>Pilihan Makanan:</h2>
    <ul>
      <li v-for="food in foods" :key="food.id" @click="selectFood(food)">
        {{ food.name }}
      </li>
    </ul>

    <!-- Pesan konfirmasi -->
    <div v-if="selectedFood">
      <p>Kamu memilih: {{ selectedFood.name }}</p>
      <button @click="resetSelection">Reset Pilihan</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Selamat Datang di Pemilihan Makanan',
      description: 'Silakan pilih makanan favoritmu dari daftar berikut:',
      foods: [
        { id: 1, name: 'Nasi Goreng' },
        { id: 2, name: 'Ayam Goreng' },
        { id: 3, name: 'Pizza' },
        { id: 4, name: 'Burger' },
        { id: 5, name: 'Sushi' },
        { id: 6, name: 'Salad' }
      ],
      selectedFood: null
    };
  },
  methods: {
    selectFood(food) {
      this.selectedFood = food;
    },
    resetSelection() {
      this.selectedFood = null;
    }
  }
};
</script>

<style scoped>
h1 {
  color: hsl(303, 39%, 49%); /* Warna hijau */
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin-bottom: 10px;
  cursor: pointer;
}
li:hover {
  text-decoration: underline;
}
button {
  margin-top: 10px;
  background-color: hsl(290, 39%, 49%);
  color: #000000;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
button:hover {
  background-color: hsl(295, 40%, 45%);
}
</style>