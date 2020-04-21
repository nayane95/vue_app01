<template>
  <div class="form-group row">
          <label for="staticEmail" class="col-sm-2 col-form-label"><h3>Search Music</h3></label>
          <div class="col-sm-10">
            <input
              type="text"
             
              class="form-control-plaintext"
              id="staticEmail"
              placeholder="Type Here"
              @input="keypressed"
            />
          </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    data(){
        return{
            newSet:[]
        }
        
    },
    methods:{
        keypressed(event){
           var key= event.target.value;
           axios.get("https://www.hpb.health.gov.lk/api/get-current-statistical")
           .then(response=>{
               this.newSet=response.data.data;
           })
           .catch(e=>{
               this.error.push(e)
           })

           this.$emit('newDataset',this.newSet)
        }
    }
}
</script>

<style>

</style>