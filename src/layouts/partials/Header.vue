<template>
  <!-- Header -->
  <header id="page-header">
   
    <slot>
      <!-- Header Content -->
      <div class="content-header">
        <!-- Left Section -->
        <div class="d-flex align-items-center">
          <!-- Toggle Sidebar -->
          <base-layout-modifier action="sidebarToggle" size="sm" variant="dual" class="mr-2 d-lg-none">
            <i class="fa fa-fw fa-bars"></i>
          </base-layout-modifier>
          <!-- END Toggle Sidebar -->

          <!-- Toggle Mini Sidebar -->
          <base-layout-modifier action="sidebarMiniToggle" size="sm" variant="dual" class="mr-2 d-none d-lg-inline-block">
            <i class="fa fa-fw fa-ellipsis-v"></i>
          </base-layout-modifier>
       
         

        
          
        </div>
        <!-- END Left Section -->

        <!-- Right Section -->
        <div class="d-flex align-items-center">
          <!-- User Dropdown -->
          <b-dropdown size="sm" variant="dual" class="d-inline-block ml-2" menu-class="p-0 border-0 font-size-sm" right no-caret>
            <template #button-content>
              <div>
              <span class="d-none d-sm-inline-block ml-1" >{{filtro.name}}<i class="fa fa-fw fa-angle-down d-none d-sm-inline-block"></i></span></div>
              
            </template>
            <li>
           
              <div class="p-2">
               
                <h5 class="dropdown-header text-uppercase">Actions</h5>
               
              
                  <a style="cursor: pointer" @click="cerrarSesion" class="cerrarSesion p-2" v-if="existeUsuario">Log Out<i class="si si-logout ml-1"></i></a>
              

              </div>
            </li>
          </b-dropdown>
          <!-- END User Dropdown -->

          <!-- Notifications Dropdown -->
          

          <!-- Toggle Side Overlay -->
         
          <!-- END Toggle Side Overlay -->
        </div>
        <!-- END Right Section -->
      </div>
      <!-- END Header Content -->

    
      <!-- Header Loader -->
      <div id="page-header-loader" class="overlay-header bg-white">
        <div class="content-header">
          <div class="w-100 text-center">
            <i class="fa fa-fw fa-circle-notch fa-spin"></i>
          </div>
        </div>
      </div>
      <!-- END Header Loader -->
    </slot>
     
  </header>
  <!-- END Header -->
</template>

<script>
import {mapState, mapActions, mapGetters } from 'vuex'




export default {
  name: 'BaseHeader',
  props: {
    classes: String
  },
  
  methods: {
    
    ...mapActions(['cerrarSesion','getTareas','eliminarTarea','getUsers']),
  
  },
   created(){
    this.getTareas(),
    this.getUsers()
  
  },
  computed: {
     ...mapState(['usuario','tareas', 'carga','users']),
    ...mapGetters(['existeUsuario']),

    filtro: function(){

      let usuario = this.usuario
     
      let userfilter = this.users.find(user => user.mail === usuario.email)


      console.log(userfilter)
     
     return userfilter
    
    },
    

},
 
}
</script>
