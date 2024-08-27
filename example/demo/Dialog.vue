<template>
  <div>
    <button class="mx-btn" @click="showDialog()">Show dialog</button>
    <dialog id="my-dialog" class="card-dialog">
      <div class="card-dialog-header">
        <h3>Date picker in a dialog</h3>
        <button type="button" class="mx-btn" style="margin: auto 0" @click="hideDialog()">
          Exit
        </button>
      </div>
      <div class="card-dialog-body">
        <date-picker
          v-model="value"
          format="YYYY-MM-DD"
          type="date"
          placeholder="Select date"
          :append-to-element="element"
        ></date-picker>
      </div>
    </dialog>
  </div>
</template>

<script>
export default {
  name: 'Dialog',
  data() {
    return {
      value: '',
      element: 'my-dialog',
    };
  },
  methods: {
    showDialog() {
      document.getElementById(this.element).showModal();
    },
    hideDialog() {
      document.getElementById(this.element).close();
    },
  },
};
</script>
