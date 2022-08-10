<template>
    <div class="about">
        <h1>About Index</h1>
        <!-- <h3>Your index {{$route.params.bodyMass}}</h3> -->
        <MassInfo></MassInfo>
          
    </div>
</template>

<script>
import MassInfo from '@/components/MassInfo.vue';

export default {
  components:{
    MassInfo,
  },
    props: {},

    setup() {
        return {};
    },
};
</script>

<style lang="scss"></style>
