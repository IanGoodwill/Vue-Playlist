<template>
    
    <li>
       {{ song.task  }}
    </li>

</template>



<script>
export default {
    name: 'Song',
    props:  [
        'song'
        
    ] 
}
</script>


<style>



</style>