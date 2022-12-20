<template lang="">
  <div class="dialog-footer">
    <button class="m-btn dialog-btn primary-btn accept-btn notify-btn" @click='closeErrDialog'>Đồng ý</button>
  </div>
</template>
<script>
export default {
  name: "ErrDialogFooter",
  emits: ["closeErrDialog"],
  methods: {
    closeErrDialog() {
      this.$emit("closeErrDialog")
    }
  }
}
</script>
