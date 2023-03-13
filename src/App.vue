<template>
  <div>
    <SelectedItems/>
    <ChooseOne />
  </div>
</template>

<script>
import SelectedItems from "./components/SelectedItems.vue";
import ChooseOne from "./components/ChooseOne.vue";

export default {
  components: {
    SelectedItems,
    ChooseOne
  }     
};
</script>
