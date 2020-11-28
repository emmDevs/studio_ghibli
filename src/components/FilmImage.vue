<template>
<div>
    <img :src="checkForImage"/>
</div>
</template>

<script>
import CastleInTheSky from '@/assets/castleinthesky.jpeg'

export default {
    name: 'film-image',
    props:['film']

}
</script>

<style>

</style>