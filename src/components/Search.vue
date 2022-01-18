<template>
   <select @change="$emit('doSearch', inputText)" v-model="inputText" id="filter">
                                <option class="All" value="All">All</option>
                            <option class="rock" value="Rock">Rock</option>
                            <option class="pop" value="Pop">Pop</option>
                            <option class="jazz" value="Jazz">Jazz</option>
                            <option class="metal" value="Metal">Metal</option>
    </select>
</template>

<script>
export default {
name: "Search",
data() {
    return {
      inputText: '',
    };
  },
}

</script>

<style>

</style>