<template>
  <div>
    <TheHeader></TheHeader>
    <TheBody></TheBody>
    <AddSaveForm></AddSaveForm>
  </div>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';
import TheBody from './components/layout/TheBody.vue';
import AddSaveForm from './components/base/AddSaveForm.vue';
export default {
  name: 'App',
  components: {
    TheHeader,
    TheBody,
    AddSaveForm
  }
}
</script>

<style>

</style>
