<template>
    
    <article>

        <h2> Different Events Using The V-On Directive</h2>

        <br>

        <section class="hidden-section" :class="{ 'section-hide': hide }">

            <p @click="Hide()"> 
                Click Me And I Vanish!
            </p>

            <br>

            <label>Count is: {{count}}</label>

            <br>

            <button v-on:click="count++">Increment</button>

            <br>     
            <br>
            <br>
            <br>

             <a @click="handleClick()">Click Me For An Alert!</a>

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
            hide: false,
            count: 0
        }
        
   
  
    },
    methods:  {
        Hide ()  {
            this.hide = !this.hide;
        },
        handleClick () {
      alert("Thanks for Clicking!");
     
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