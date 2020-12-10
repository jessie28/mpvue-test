<template>
    <div>
        <web-view :src="aSrcs"></web-view>
    </div>
</template>

<script>


export default {

  data () {
    return {
      aSrcs:'https://mp.tangche.com/tms/login'
    }
  }
}
</script>

<style scoped>

</style>
