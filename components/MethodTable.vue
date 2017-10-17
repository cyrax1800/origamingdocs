<template>
  <div class="card">
    <header class="card-header">
      <p class="card-header-title">{{title}}</p>
      <a href="#" class="card-header-icon" aria-label="more options">
        <span class="icon"><i class="fa fa-angle-down" aria-hidden="true"></i></span>
      </a>
    </header>
    <div class="card-content is-paddingless">
      <div class="content">
        <table class="table is-bordered">
          <thead>
            <tr>
              <th class="is-narrow">Return Type</th>
              <th class="is-narrow">Name</th>
              <th class="is-narrow">Parameter</th>
              <th>Description</th>
            </tr>
          </thead>
          <tbody>
            <method-row v-for="method in methods" :key="method.name" v-bind:method="method"></method-row>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
  import MethodRow from '~/components/MethodRow.vue'

  export default {
    components: {
      MethodRow
    },
    props: ['title', 'methods'],
    mounted () {
    },
    data () {
      return {
      }
    },
    methods: {
    }
  }
</script>