<template>
  <div class="input-group">
    <label>{{ label }}</label>
    <input :type="type" :placeholder="placeholder" />
  </div>
</template>

<script>
export default {
  props: ['label', 'placeholder', 'type'],
};
</script>

<style lang="scss"></style>
