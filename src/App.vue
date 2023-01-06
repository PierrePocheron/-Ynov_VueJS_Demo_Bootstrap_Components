<template>
  <div>
    <h1>Title App</h1>

    <p>
      Theme :
      <select v-model="theme">
        <option value="primary">primary</option>
        <option value="danger">danger</option>
      </select>
    </p>

    <p>
      Size :
      <select v-model="size">
        <option value="sm">sm</option>
        <option value="md">md</option>
        <option value="lg">lg</option>
      </select>
    </p>

    <MyButton theme="theme" size="size" disabled="disabled"
      >Button du theme</MyButton
    >

    <MyButton theme="warning" size="sm">Remplace le slot</MyButton>
    <MyButton theme="warning" size="sm" :disabled="true"
      >Remplace le slot</MyButton
    >
    <MyButton theme="danger" size="lg">Nom bouton 2</MyButton>
    <MyButton theme="danger" size="lg" disabled block loading
      >Nom bouton 2</MyButton
    >
    <MyButton>Buuton default</MyButton>
  </div>
</template>

<script>
import MyButton from "@/components/MyButton.vue";
export default {
  components: {
    MyButton,
  },

  data() {
    return {
      theme: "primary",
      size: "md",
      disabled: false,
      block: false,
    };
  },
};
</script>
