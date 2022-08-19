<template>
  <form>
    <label>Please add in item (press 'alt' & '+' to add it to the list)</label>
    <input v-model="tempItem" type="text" @keyup.alt="addItem" />
  </form>
</template>

<script>
export default {
  data() {
    return {
      tempItem: '',
      items: [],
    };
  },
  methods: {
    addItem(e) {
      if (e.key === '+' && this.tempItem) {
        if (!this.items.includes(this.tempItem)) {
          this.items.push(this.tempItem);
        }
        this.tempItem = '';
      }
      this.$emit('data', this.items);
    },
  },
};
</script>

<style></style>
