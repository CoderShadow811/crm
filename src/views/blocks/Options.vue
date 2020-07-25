<template>
  <div>

  
    <!-- Page Content -->
    <div class="content">

      <!-- Bootstrap Buttons in Options -->
      <b-row>
        <b-col md="6">
          <base-block title="Nombre de la tarea" subtitle="Anibal Gaytán">
            <template #options>
              <b-button size="sm" variant="primary">Edit</b-button>
              <b-button size="sm" variant="danger">Delete</b-button>
            </template>
            <p>
              Dolor posuere proin blandit accumsan senectus netus nullam curae, ornare laoreet adipiscing luctus mauris
              adipiscing pretium eget fermentum, tristique lobortis est ut metus lobortis tortor tincidunt himenaeos
              habitant quis dictumst proin odio sagittis purus mi, nec taciti vestibulum quis in sit varius lorem sit
              metus mi.
            </p>
          </base-block>
        </b-col>
        <b-col md="6">
          <base-block title="Nombre de la tarea" subtitle="Andres Ramírez" header-rtl>
            <template #options>
              <b-button size="sm" variant="primary">Edit</b-button>
              <b-button size="sm" variant="danger">Delete</b-button>
            </template>
            <p>
              Dolor posuere proin blandit accumsan senectus netus nullam curae, ornare laoreet adipiscing luctus mauris
              adipiscing pretium eget fermentum, tristique lobortis est ut metus lobortis tortor tincidunt himenaeos
              habitant quis dictumst proin odio sagittis purus mi, nec taciti vestibulum quis in sit varius lorem sit
              metus mi.
            </p>
          </base-block>
        </b-col>
      </b-row>
      
  
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    loadData (ref) {
      // Set the block to loading state
      this.$refs[ref].stateLoading()

      // .. here you could load your data

      // Set a timeout for demo purposes
      setTimeout(() => {
        // Set the block back to normal state
        this.$refs[ref].stateNormal()
      }, 2000)
    }
  }
}
</script>