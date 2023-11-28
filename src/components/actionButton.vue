<script>
export default {
  name: 'actionButton',
  props: {
    msg: {
      type: String,
      required: true,
      default: function() {
        return "Valider"
      }
    }
  },
  data() {
    return {

    }
  }
}

</script>

<template>
    <button class="btn">{{ msg }}</button>
</template>

<style>
.btn {
    padding: 8px 20px;
    border-radius: 10px;
    border: 0;
    margin: 10px;
    cursor: pointer;
}

</style>