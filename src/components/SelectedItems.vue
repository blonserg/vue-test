<template>
  <div>
    <div>
      <h3>Выбранные вещи:</h3>
      <ul>
        <li v-for="item in selectedItems" :key="item">{{ item.name }}</li>
      </ul>
    </div>
    <div>
      <h3>Выберите от 1 до 6 вещей:</h3>
      <div v-for="item in userItems" :key="item.id">
        <label>
          <input type="checkbox" :value="item" v-model="checkedItems" :disabled="disableCheckbox(item)">{{ item.name }}
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
      checkedItems: [],
    };
  },
  methods: {
    disableCheckbox(item) {
      return !this.checkedItems.includes(item) && this.selectedItems.length === 6;
    }
  },
  computed: {
    selectedItems() {
      return this.checkedItems.slice(0, 6);
    }
  },
};
</script>
