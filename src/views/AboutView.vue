<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ text }}
    {{ data }}
    <button type="button" class="btn btn-primary">Primary</button>
  </div>
  <i class="bi-alarm"></i>
  <!-- Button trigger modal -->
  <button
    type="button"
    class="btn btn-primary"
    data-bs-toggle="modal"
    data-bs-target="#exampleModal"
  >
    Launch demo modal
  </button>

  <!-- Modal -->
  <div
    class="modal fade"
    id="exampleModal"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">...</div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
          <button type="button" class="btn btn-primary">Save changes</button>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: '我叫yuling',
      data: {}
    }
  },
  mounted() {
    console.log(import.meta.env.VITE_PATH)
    console.log(import.meta.env.VITE_TEXT)
    const url = import.meta.env.VITE_PATH
    this.$http.get(url).then((response) => {
      console.log(response.data)
      this.data = response.data
    })
  }
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    /* min-height: 100vh; */
    display: flex;
    /* align-items: center; */
    flex-direction: column;
    justify-content: center;
  }
}
</style>
