<template>
    
    <article>

        <h2> Different Events Using The V-On Directive</h2>

        <br>

        <section class="hidden-section" :class="{ 'section-hide': hide }">

            <p @click="Hide()"> 
                Click Me And I Vanish!
            </p>

            <br>

            <h4>
                Click Me To Show the Date!
            </h4>

        </section>

   <br>
   <br>
   <br>

    </article>

</template>



<script>


export default {
    name: 'Events',
       data ()  {
        return  {
            hide: false
        }
    },
    methods:  {
        Hide ()  {
            this.hide = !this.hide;
        }
    }
  
   
}
</script>



<style>
.hidden-section p {
    max-height: 100px;
    overflow: hidden;
    transition: 0.3s ease all;
}

.section-hide p {
    max-height: 0;
}
</style>