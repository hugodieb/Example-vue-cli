<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User name : {{ myName }} </p>
        <p>User name reverse: {{ switchName() }} </p>
        <p>User age: {{ userAge }} </p>
        <button @click="resetName">Reset Name</button>
        <button @click="resetFn">Reset Name Fn</button>
        <button @click="resetAge">Reset Age</button>
    </div>
</template>

<script>
  export default {
    /*props: ['myName'],*/
    props: {
      myName: {
        type: String,
      },
      resetFn: Function,
      userAge: Number,
    },
    methods: {
      switchName() {
        return this.myName.split("").reverse().join("");
      },
      resetName() {
        this.myName = "Sheik";
        this.$emit('nameWasReset', this.myName);
      },
      resetAge() {
        this.userAge = 45;
        this.$emit('ageWasReset', this.userAge);
      },
    },
  }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
