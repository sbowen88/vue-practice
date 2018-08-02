<template>
    <div class="test">
        <h1>{{title}}</h1>
        <p v-if = "showName">{{user.firstName}}</p>
        <p v-else></p>
    </div>
</template>


<script>
export default {
  name: "test",
  data() {
    return {
      title: "Hello World",
      user:{
          firstName: "Scott",
          lastName: "Smith"
      },
      showName: false
    };
  }
};
</script>

<style scoped>
</style>

