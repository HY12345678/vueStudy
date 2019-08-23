<template>
  <input type="text" class="form-control" :value="val"
  @input="$emit('change',$event.target.value)"/>
</template>

<script>
export default {
    props:['val'],
    model:{
        prop:'val',
        event:'change'
    }
}
</script>

<style>

</style>