<template>
<div>
<form @submit.prevent="submitData">
    <div>
      <h1> Add User's Data </h1>
      <label>Name: </label>
      <input type="text" v-model="enteredName" />
    </div>
    <div>
      <label>Age: </label>
      <input type="text" v-model="enteredAge" />
    </div>
    <div>
      <button>Add User</button>
    </div>
  </form>

</div>
   
</template>

<script>
export default {
    emits: ['add-user'],
    data() {
        return {
            enteredName: '',
            enteredAge: '',
        }
    },
    methods: {
    submitData() {
      this.$emit(
        'add-user',
        this.enteredName,
        this.enteredAge,
      );
    },
  },

}
</script>