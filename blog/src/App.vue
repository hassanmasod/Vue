<template>
  <div class="main-page">     
        <HEADER/>
       
        <div class="main">        
          <sidebar/> 
          
          <HelloWorld/>
            
        </div>
    </div>
  
  
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import HEADER from './components/header.vue'
import sidebar from './components/sidebar.vue'



export default {
  name: 'App',
  components: {
    HelloWorld,
    sidebar,
    HEADER,
    
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
 }
 .main
 {
  display: flex;
 }


</style>
