<template>
  <span>
    <span v-if="type.isDictionary">
      Dictionary&lt;<key :type="type.key"></key>,
      <value :type="type.value"></value>&gt;
    </span>
    <template v-else>
      <nuxt-link v-if="type.link != ''" :to="getLink(type.link)" class="text-bold">{{type.name}}</nuxt-link>
      <span v-else class="text-modifiers">{{type.name}}</span>

      <template v-if="type.generic.isGeneric == true">
        <span>&lt;</span>
        <nuxt-link v-if="type.generic.link != ''" :to="getLink(type.generic.link)" class="text-bold">{{type.generic.genericType}}</nuxt-link>
        <span v-else class="text-modifiers">{{type.generic.genericType}}</span>
        <span>&gt;</span>
      </template>
    </template>
  </span>
</template>

<script>
  import TypeName from '~/components/TypeName.vue'

  export default {
    props: ['type'],
    beforeCreate () {
      this.$options.components.key = TypeName
      this.$options.components.value = TypeName
    },
    mounted () {
      // console.log(this.type.name)
    },
    data () {
      return {
        tipe: {}
      }
    },
    methods: {
      getLink: function (name) {
        return '/docs/' + name
      }
    }
  }
</script>