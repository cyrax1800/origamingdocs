<template>
  <tr>
    <td class="is-narrow">
      <modifiers :item="method"></modifiers>
      <type-name v-if="method.hasOwnProperty('returnType')" :type="method.returnType"></type-name>
    </td>
    <td class="is-narrow">{{method.name}}</td>
    <td class="is-narrow">
      <template v-for="param in method.parameters">
        <p><type-name :type="param.type"></type-name> {{param.name}}<span class="text-purple text-bold">{{defaultValue(param)}}</span></p>
      </template>
    </td>
    <td>{{method.desc}}</td>
  </tr>
</template>

<script>
  import TypeName from '~/components/TypeName.vue'
  import Modifiers from '~/components/Modifiers.vue'

  export default {
    components: {
      TypeName,
      Modifiers
    },
    props: ['method'],
    mounted () {
    },
    data () {
      return {
      }
    },
    methods: {
      defaultValue: function (param) {
        if (param.hasOwnProperty('defaultValue')) {
          if (param.defaultValue == null) {
            return ' = null'
          } else {
            return ' = ' + param.defaultValue.toString()
          }
        }
      }
    }
  }
</script>