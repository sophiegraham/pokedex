<template>
  <form v-on:submit.prevent="handleSubmit">
    <select v-model="sort">
      <option value="pokemon">Name</option>
      <option value="type_1">Type</option>
      <option value="attack">Attack</option>
      <option value="defence">Defense</option>
    </select>
    <label>
      <input type="radio" value="1" name="direction" v-model="direction"
      v-on:change="handleSubmit"> asc
    </label>
    <label>
      <input type="radio" value="-1" name="direction" v-model="direction"
      v-on:change="handleSubmit"> desc
    </label>
    <button>Apply Sort</button>
  </form>
</template>

<script>
export default {
  props: {
    onSort: Function
  },
  data() {
    return {
      sort: 'pokemon',
      direction: 1
    };
  },
  methods: {
    handleSubmit() {
      this.onSort({
        sort: this.sort, 
        direction: this.direction
      });
    }
  }
};
</script>

<style>
</style>