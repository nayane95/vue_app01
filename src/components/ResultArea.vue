<template>
  <div class="container">
    <h2>අද දිනට COVID 19 තතු</h2>
    <div class="row">
      <div class="col-md-4">
        <div class="card border-danger mb-3" style="max-width: 20rem;">
          <div class="card-header">නව ආසාදිතයින් සංඛ්‍යාව</div>
          <div class="card-body">
            <h1 class="card-title">{{results.local_new_cases}}</h1>
          </div>
        </div>
      </div>
      <div class="col-md-4">
        <div class="card border-warning mb-3" style="max-width: 20rem;">
          <div class="card-header">දැනට ප්‍රතිකාර ලබන රෝගීන් සංඛ්‍යාව</div>
          <div class="card-body">
            <h1 class="card-title">{{results.local_active_cases}}</h1>
          </div>
        </div>
      </div>
      <div class="col-md-4">
        <div class="card border-info mb-3" style="max-width: 20rem;">
          <div class="card-header">තහවුරු කල රෝගීන් සංඛ්‍යාව</div>
          <div class="card-body">
            <h1 class="card-title">{{results.local_total_cases}}</h1>
          </div>
        </div>
      </div>
    </div>

    <div class="card border-danger mb-3" style="max-width: 20rem;">
      <div class="card-header">දැනට සිදු වී ඇති මරණ සංඛ්‍යාව</div>
      <div class="card-body">
        <h1 class="card-title">{{results.local_deaths}}</h1>
      </div>
    </div>
    <div class="card border-success mb-3" style="max-width: 20rem;">
      <div class="card-header">දැනට සම්පූර්ණ සුවය ලබා ඇති සංඛ්‍යාව</div>
      <div class="card-body">
        <h1 class="card-title">{{results.local_recovered}}</h1>
      </div>
    </div>
    <div class="card border-warning mb-3" style="max-width: 20rem;">
      <div class="card-header">COVID-19 වැළදී ඇති බවට සැක සහිත පුද්ගලයින් සංඛ්‍යාව</div>
      <div class="card-body">
        <h1 class="card-title">{{results.local_total_number_of_individuals_in_hospitals}}</h1>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      results: []
    };
  },
  mounted() {
    axios
      .get("https://www.hpb.health.gov.lk/api/get-current-statistical")
      .then(response => {
        this.results = response.data.data;
      })
      .catch(e => {
        this.error.push(e);
      });
  }
};
</script>

<style>
</style>