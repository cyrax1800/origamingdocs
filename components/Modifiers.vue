<template>
  <span class="text-modifiers">
    {{defineModifiers()}}
  </span>
</template>

<script>
  export default {
    props: ['item'],
    mounted () {
    },
    data () {
      return {
      }
    },
    methods: {
      defineModifiers: function () {
        var result = ''
        if (this.item.isPublic) {
          result += 'public '
        } else if (this.item.isProtected) {
          result += 'protected '
        } else {
          result += 'private '
        }

        if (this.item.isStatic) {
          result += 'static '
        }

        return result
      }
    }
  }
</script>