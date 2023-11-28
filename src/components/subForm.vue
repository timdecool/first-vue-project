<script>
export default {
  name: 'subForm',
  props: {
    inputs: {
      type: Object,
      required: true,
      default: function() {
        return [
            { 
                type: "text",
                name: "name",
            },
            {
                type: "submit",
                name: "submit"
            }
        ]
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
    <form>
        <div v-for="input of inputs">
            <label :for="input.name">{{ input.name }}</label>
            <input :type="input.type" :name="input.name" :id="input.name">
        </div>
    </form>
</template>

<style>
    form {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }

    form>div {
        display: flex;
        flex-direction: column;
    }

    input {
        padding: 10px;
        width: 100%;
        border-radius: 10px;
        border: 0;
    }

    label {
        margin-left: 10px;
    }


</style>