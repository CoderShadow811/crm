<template>
  <!-- Footer -->
  <footer id="page-footer">
    <slot>
      <div class="content py-3">
        <b-row class="font-size-sm">
          <b-col class="py-1 text-center text-sm-right">
           <img alt="Ennoble" data-src="https://ennobledesign.co/wp-content/uploads/2020/05/Ennoble-Design-Logo-100x100-1.png" class="logofooter" src="https://ennobledesign.co/wp-content/uploads/2020/05/Ennoble-Design-Logo-100x100-1.png"> Developed by <a class="font-w600" href="https://ennobledesign.co/" target="_blank">Ennoble Design</a> 
          </b-col>
        
        </b-row>
      </div>
    </slot>
  </footer>
  <!-- END Footer -->
</template>

<script>
export default {
  name: 'BaseFooter',
  props: {
    classes: String
  }
}
</script>
<style>
.logofooter{
    max-height: 40px;
    padding-bottom: 4px;
}
</style>