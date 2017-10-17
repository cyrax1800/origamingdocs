<template>
  <div>
    <h1 class="title is-1">{{preData.name}}</h1>
    <table class="table">
      <tbody>
        <tr>
          <td class="is-narrow">Package</td>
          <td>{{preData.package}}</td>
        </tr>
        <tr>
          <td class="is-narrow">Class</td>
          <td>{{preData.class}}</td>
        </tr>
        <tr>
          <td class="is-narrow">Inheritance</td>
          <td v-if="preData.inheritances.length > 0">{{preData.name}} 
            <template v-for="inheritance in preData.inheritances">
              <span class="icon"><i class="fa fa-arrow-right" aria-hidden="true"></i></span>
              <type-name :type="inheritance"></type-name>  
            </template>
          </td>
          <td v-else>-</td>
        </tr>
        <tr>
          <td class="is-narrow">Implements</td>
          <td v-if="preData.implements.length > 0">
            <template v-for="implemnetType in preData.implements">
              <type-name :type="implemnetType"></type-name>  
              <span>; </span>
            </template>
          </td>
          <td v-else>-</td>
        </tr>
      </tbody>
    </table>
    <p>{{preData.desc}}</p>
    <br>

    <property-table v-if="preData.constants.length > 0" title="Constants" :fields="preData.constants"></property-table>
    <property-table v-if="preData.fields.length > 0" title="Field / Property" :fields="preData.fields"></property-table>

    <method-table v-if="preData.constructors.length > 0" title="Constructor" :methods="preData.constructors"></method-table>    
    <method-table v-if="preData.publicMethods.length > 0" title="Public Method" :methods="preData.publicMethods"></method-table>    
    <method-table v-if="preData.privateMethods.length > 0" title="Private Method" :methods="preData.privateMethods"></method-table>    

  </div>
</template>

<script>
  import axios from 'axios'
  import TypeName from '~/components/TypeName.vue'
  import PropertyTable from '~/components/PropertyTable.vue'
  import MethodTable from '~/components/MethodTable.vue'

  export default {
    components: {
      TypeName,
      PropertyTable,
      MethodTable
    },
    async asyncData (context) {
      let { data } = await axios.get(`http://localhost:3000/docs_data/` + context.params[0] + `.json`)
      return {
        preData: data
      }
    },
    mounted () {
      this.inheritances = this.preData.inheritances
      this.implements = this.preData.implements
      this.constants = this.preData.constants
      this.fields = this.preData.fields
      this.constructors = this.preData.constructors
      this.publicMethods = this.preData.publicMethods
      this.privateMethods = this.preData.privateMethods
    },
    data () {
      return {
        inheritances: [],
        implements: [],
        constants: [],
        fields: [],
        constructors: [],
        publicMethods: [],
        privateMethods: []
      }
    },
    methods: {
    }
  }
</script>