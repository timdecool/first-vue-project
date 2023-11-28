<script>
export default {
  name: 'SousComposant',
  props: {
    msg: {
      type: [String,Number],
      required: false,
      default: function() {
        return "SousComposant"
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
    <section>
        <p>
            {{ msg }}
        </p>
    </section>

</template>

<style scoped>

</style>
