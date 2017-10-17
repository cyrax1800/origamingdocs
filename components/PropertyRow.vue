<template>
  <tr>
    <td class="is-narrow">
      <modifiers :item="field"></modifiers>
      <type-name :type="field.type"></type-name>
    </td>
    <td class="is-narrow">{{field.name}}</td>
    <td>{{field.desc}}</td>
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
    props: ['field'],
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