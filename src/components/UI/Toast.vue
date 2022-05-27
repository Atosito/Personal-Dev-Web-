<script>
export default {
    name:"Toast",
   props: ['status', 'text'],
    computed: {
        toastStatus() {
            console.log(this.status)
            return this.status;
        }
    }
}
</script>

<template>
  <div class="toast-wrapper">
    <div v-bind:class="toastStatus" class="toast">
      {{ text }}
    </div>
  </div>
</template>

<style>
.toast-wrapper {
  position: fixed;
  width: 100%;
  top: 20px;
}
.toast {
  padding: 20px;
  color: white;
  background: #ff0062;
  border-radius: 10px;
  box-shadow: 1px 3px 5px rgba(0, 0, 0, 0.2);
  max-width: 400px;
  margin: 0 auto;
}

.success {
  background: #06c012;
}

.error {
  background: #c30303;
}
</style>
