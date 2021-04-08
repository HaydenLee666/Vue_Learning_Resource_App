<template>
  <base-dialog v-if="isInvalid" title="Invalid Input" @close="confirmError">
    <template #description>
      <p>At least one input value is invalid!</p>
      <p>Please check it.</p>
    </template>
    <template #actions>
      <base-button @click="confirmError">OK</base-button>
    </template>
  </base-dialog>
  <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" v-model="title" />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea
          id="description"
          name="description"
          row="3"
          v-model="description"
        ></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" v-model="link" />
      </div>
      <div>
        <base-button type="submit">Add Resource</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  inject: ['addResource'],
  data() {
    return {
      title: '',
      description: '',
      link: '',
      isInvalid: false
    };
  },
  methods: {
    submitData() {
      if (
        this.title.trim() === '' ||
        this.description.trim() === '' ||
        this.link.trim() === ''
      ) {
        this.isInvalid = true;
        return;
      }
      this.addResource(this.title, this.description, this.link);
      this.title = this.description = this.link = '';
    },
    confirmError() {
      this.isInvalid = false;
    }
  }
};
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>