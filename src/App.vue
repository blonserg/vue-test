<template>
  <div>
    <div>
      <h3>Выбранные вещи:</h3>
      <ul>
        <li v-for="id in selectedItems" :key="id">{{ getUserItem(id).name }}</li>
      </ul>
    </div>
    <div>
      <h3>Выбранные вещи:</h3>
      {{ selectedItem }}
    </div>
    <div>
      <h3>Выберите от 1 до 6 вещей:</h3>
      <div v-for="item in userItems" :key="item.id">
        <label>
          <input type="checkbox" v-model="selectedItems" :value="item.id">{{ item.name }}
        </label>
      </div>
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
      userItems: [
        {
            "id": 1,
            "name": "Shoes 1"
        },
        {
            "id": 2,
            "name": "Shoes 2"
        },
        {
            "id": 3,
            "name": "Shoes 3"
        },
        {
            "id": 4,
            "name": "Shoes 4"
        },
        {
            "id": 5,
            "name": "T-shirt 1"
        },
        {
            "id": 6,
            "name": "T-shirt 2"
        },
        {
            "id": 7,
            "name": "T-shirt 3"
        },
        {
            "id": 8,
            "name": "T-shirt 4"
        }
      ],
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
      selectedItems: [],
    };
  },
  methods: {
    getItemById(id) {
      return this.userItems.find((item) => item.id === id);
    },
    getUserItem(id) {
      return this.userItems.find((item) => item.id === id);
    }
  },
  computed: {
    isMaxSelected() {
      return this.selectedItems.length >= 6;
    },
  },
};
</script>
