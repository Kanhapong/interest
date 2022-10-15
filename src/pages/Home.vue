<template>
  <navbar />
  <section class="home">

    <div class="image">
        <img src="images/Lx.png" alt="">
    </div>

    <div class="content">
        <h3>{{name}}</h3>
        <span>{{motto}}</span>
        <p>{{content}}</p>
        <a href="/about" class="btn"> about me <i class="fas fa-user"></i> </a>
    </div>

</section>
</template>

<script>
import Navbar from '../components/Navbar.vue'
export default {
  components: { Navbar },
      data() {
        return {
            name: "Apex legends",
            motto: "Battle royale Game",
            content: "An online multiplayer battle royale game featuring squads of three players using pre-made characters with distinctive abilities, called 'Legends' similar to those of hero shooters.",
        }
    }

}
</script>

<style>

</style>