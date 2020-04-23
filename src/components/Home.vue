<template>
  <div class="container"> 
    <form>
      <fieldset>
        <legend>Corona Tracker</legend>
        <!-- <app-search @newDataset="results = $event"></app-search> -->
       
      </fieldset>
    </form>
    <div class="container">
      <div class="col-md-12">
            <app-result></app-result>  
      </div> 
    </div>
  </div>

  
</template>

<script>
import SearchArea from './SearchArea.vue'
import ResultArea from './ResultArea.vue'

export default{
    
    data(){
        
    },
    components:{
        'app-search':SearchArea,
        'app-result':ResultArea
    }
    
}
    
</script>

<style>
</style>