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
              <th class="is-narrow">Type</th>
              <th class="is-narrow">Name</th>
              <th>Description</th>
            </tr>
          </thead>
          <tbody>
            <property-row v-for="field in fields" :key="field.name" v-bind:field="field"></property-row>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
  import PropertyRow from '~/components/PropertyRow.vue'

  export default {
    components: {
      PropertyRow
    },
    props: ['title', 'fields'],
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