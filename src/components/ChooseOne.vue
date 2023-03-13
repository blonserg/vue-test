<template>
  <div>
    <div>
      <h3>Выбранные вещи:</h3>
      {{ selectedItem }}
    </div>
    <div>
      <h3>Выберите одну вещь:</h3>
      <div v-for="item in chooseItem" :key="item.id">
        <label>
          <input type="radio" v-model="selectedItem" :value="item.name">{{ item.name }}
        </label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      chooseItem: [
        {
            "id": 11,
            "name": "Jacket 1"
        },
        {
            "id": 12,
            "name": "Jacket 2"
        },
        {
            "id": 13,
            "name": "Jacket 3"
        },
        {
            "id": 14,
            "name": "Jacket 4"
        },
        {
            "id": 15,
            "name": "Hoodie 1"
        },
        {
            "id": 16,
            "name": "Hoodie 2"
        },
        {
            "id": 17,
            "name": "Hoodie 3"
        },
        {
            "id": 18,
            "name": "Hoodie 4"
        }
      ],
      selectedItem: null,
    };
  },
};
</script>
