<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>Edit me!</p>
        <p>Name: {{myName}}</p>
        <p>Age: {{userAge}}</p>
        <button @click="editAge">Edit Age</button>
        <button @click="changeName">Change Name</button>
    </div>
</template>

<script>
  export default {
    props: {
      userAge: {
        type: Number,
      },
      myName: {
        type: String,
      },
    },
    methods: {
      editAge() {
        this.userAge = 30;
        this.$emit('ageWasReset', this.userAge);
      },
      changeName() {
        this.myName = "Leonardo";
        this.$emit('nameWasReset', this.myName);
      },
    },
  }
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>
