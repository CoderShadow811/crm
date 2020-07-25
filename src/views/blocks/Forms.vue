<template>
  <div>
    <!-- Hero -->
    <base-page-heading title="User Registration" subtitle="">
      <template #extra>
        <b-breadcrumb class="breadcrumb-alt">
          <b-breadcrumb-item href="javascript:void(0)">User</b-breadcrumb-item>
          <b-breadcrumb-item active>Registration</b-breadcrumb-item>
        </b-breadcrumb>
      </template>
    </base-page-heading>
    <!-- END Hero -->

    <!-- Page Content -->
    <div class="content">
      <!-- Form Submission in Options -->
    
        
          <b-form  @submit.prevent="crearUsuario({email:email,password:pass1,nombre:nombre,lastname:lastname,rol:rol})">
            <base-block title="User register" header-bg>
              <template #options>
                <b-button type="submit" size="sm" variant="primary" :disabled="!desactivar">
                  Submit
                </b-button>
                
              </template>
              <b-row class="justify-content-center py-sm-3 py-md-5">
                <b-col sm="10" md="8">
                  
               <b-form-group label="Select" label-for="skill">
                <template #label>
                  Rol<span class="text-danger">*</span>
                </template>
                <b-form-select id="Rol" label-for="block-form1-rol" name="Rol" :options="options" v-model="rol" ></b-form-select>
                <b-form-invalid-feedback id="skill-feedback">
                  Please select a rol!
                </b-form-invalid-feedback>
              </b-form-group>
              
                  <b-form-group label="Name" label-for="block-form1-name">
                    <b-form-input id="block-form1-password" class="form-control-alt" v-model="nombre" type="text" placeholder="Name"></b-form-input>
                  </b-form-group>
                     <b-form-group label="Last Name" label-for="block-form1-name">
                    <b-form-input id="block-form1-password" class="form-control-alt" v-model="lastname" type="text" placeholder="Last Name"></b-form-input>
                  </b-form-group>
                  <b-form-group label="Email" label-for="block-form1-username">
                    <b-form-input id="block-form1-username" class="form-control-alt" v-model="email" placeholder="Enter your Email.."></b-form-input>
                  </b-form-group>
                  <b-form-group label="Password" label-for="block-form1-password">
                    <b-form-input id="block-form1-password" class="form-control-alt" v-model="pass1" type="password" placeholder="Enter your password"></b-form-input>
                  </b-form-group>
                    
                  <b-form-group label="Confirm Password" label-for="block-form1-password">
                    <b-form-input id="block-form1-password" class="form-control-alt" v-model="pass2" type="password" placeholder="Confirm password"></b-form-input>
                   </b-form-group>
            
                </b-col>
 {{error}}
              </b-row>
                    
            </base-block>
           
          </b-form>
      
      <!-- END Form Submission in Options -->
    </div>
    <!-- END Page Content -->
  </div>
</template>

<script>

import { mapActions, mapState } from 'vuex'

export default {
    name: 'Registro',
    data() {
        return {
           options: [
        { value: null, text: 'Please select' },
        { value: 'admin', text: 'Admin' },
        { value: 'seller', text: 'Seller' },
       
      ],
            email: '',
            pass1: '',
            pass2: '',
            nombre: '',
            rol:'',
            lastname:'',
        }
    },
    methods: {
        ...mapActions(['crearUsuario']),
        
        
    },computed: {
        ...mapState(['error']),
        desactivar(){
            return this.pass1 === this.pass2 && this.pass1 != ''
        }
    },
  
    
}
</script>
