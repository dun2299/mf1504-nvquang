<template>
  <div class="m-input-box" >
    <label for="" class="m-input-label">{{fieldLabel}} <div class="m-input-title-require">&nbsp;*</div></label>
    <input type="text" m-required field-label={{fieldLabel}} class="m-input" id="employeeCode" property-name={{propertyName}}>
  </div>
</template>

<script>
export default {
    name: "MInput",
    props: {
        fieldLabel: String,
        propertyName: String
    }
}
</script>

<style scoped>
    @import url(../../css/style.css);
</style>