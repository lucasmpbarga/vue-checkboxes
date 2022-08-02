<template>
  <div>
    <input
      type="checkbox"
      :id="id"
      :name="name"
      :checked="isChecked"
      @click="$emit('check-event', id)"
    />
    <label for="scales">{{ this.$props.name }}</label>
  </div>
</template>

<script>
export default {
  props: {
    id: String,
    name: String,
    isChecked: Boolean,
  },
  mounted() {
    console.log("props", this.$props);
  },
  methods: {
    print() {
      console.log("props", this.$props);
    },
  },
};
</script>

<style scoped>
.swatcher_item {
  background: #eee;
  display: inline-block;
  width: 30px;
  height: 30px;
  margin: 4px;
  border-radius: 60px;
  position: relative;
  cursor: pointer;
}
.swatcher_item:hover,
.swatcher_item.active {
  box-shadow: 0 0 2px rgba(0, 0, 0, 0.9);
}
.swatcher_item.active svg {
  position: absolute;
  top: 5px;
  left: 5px;
  width: 20px;
  height: 20px;
}
</style>
