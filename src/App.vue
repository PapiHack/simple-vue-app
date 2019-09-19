<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <br>
        <button class="pull-right btn btn-default" @click="selectedComponent = null">Reset Template</button>
        <button class="btn btn-primary" @click="loadComponent('appBlue')">Load Blue Template</button>
        <button class="btn btn-success" @click="loadComponent('appGreen')">Load Green Template</button>
        <button class="btn btn-danger" @click="loadComponent('appRed')">Load Red Template</button>
        <hr>
        <component :is="selectedComponent" v-if="selectedComponent">
          {{ message }}
        </component>
        <div v-else>
          <app-blue></app-blue>
          <app-green></app-green>
          <app-red></app-red>
        </div>
      </div>
    </div>  
  </div>
</template>

<script>
  import Blue from '../src/components/Blue'
  import Red from '../src/components/Red'
  import Green from '../src/components/Green'

  export default {
    components: {
      appBlue: Blue,
      appGreen: Green,
      appRed: Red,
    },
    data() {
      return {
        selectedComponent: null,
        message: ''
      }
    },
    methods: {
      loadComponent(cmp) {
        this.selectedComponent = cmp
        switch(cmp){
          case 'appBlue': this.message = 'The Blue Template is selected !'
                          break
          case 'appGreen': this.message = 'The Green Template is selected !'
                            break
          case 'appRed' : this.message = 'The Red Template is selected !'
                            break
        }
      }
    }
  }
</script>