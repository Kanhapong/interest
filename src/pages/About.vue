<template>
    <div>
        <navbar />
        <section class="about">

            <h1 class="heading"> my <span>account</span> </h1>

            <div class="row">

                <div class="info-container">

                    <h1>personal info</h1>

                    <div class="box-container">

                        <div class="box">
                            <h3> <span>name : </span>{{name}}</h3>
                            <h3> <span>experience : </span>{{experience}}</h3>
                            <h3> <span>skills : </span>{{skill}}</h3> 
                            <h3> <span>server : </span>{{server}}</h3>
                            <h3> <span>platfrom : </span>{{platform}}</h3>
                        </div>

                    </div>

                </div>

                <div class="count-container">

                    <div class="box">
                        <h3>4+</h3>
                        <p>years of experiences</p>
                    </div>

                    <div class="box">
                        <h3>4+</h3>
                        <p>Rank Diamonds</p>
                    </div>

                    <div class="box">
                        <h3>5+</h3>
                        <p>heirloom</p>
                    </div>

                    <div class="box">
                        <h3>2+</h3>
                        <p>scrims</p>
                    </div>

                </div>

            </div>

        </section>

        <!-- about section ends -->

        <!-- skills section starts  -->

        <section class="skills">

            <h1 class="heading"> <span>Character</span> legends </h1>

            <div class="box-container">
                <div class="box" v-for="s in skills" :key="s.name">
                    <img :src="s.image">
                    <h3>{{s.name}}</h3>
                </div>

            </div>

        </section>

        <!-- skills section ends -->

        <!-- education section starts  -->

        <section class="education">

            <h1 class="heading"> <span>my</span> experience </h1>

            <div class="box-container">

                <div class="box" v-for="e in experiences" :key="e.years">
                    <div class="box">
                        <i class="fas fa-briefcase"></i>
                        <span>{{e.years}}</span>
                        <h3>{{e.company}}</h3>
                        <p>{{e.jobs}}</p>
                    </div>
                </div>

            </div>

        </section>
    </div>
</template>

<script>
import Navbar from '../components/Navbar.vue'
import axios from "axios"
export default {
    components: { Navbar },
    methods: {
        async fetchExperince() {
            try {
                let res = await axios.get("https://634a3bbf5df95285140dc3c2.mockapi.io/rank/v1/rank")
                this.experiences = res.data
            } catch (error) {
            }
        },
        async fetchSkill() {
            try {
                let res = await axios.get("https://634a284333bb42dca4ff159e.mockapi.io/todo/v1/todo")
                this.skills = res.data
            } catch (error) {

            }
        }

    },
    data() {
        return {
            name: "Zelig",
            skill: "Movement, Aimming",
            experience: "4 years",
            server: "Singapore",
            platform: "PC",
            experiences: [],
            skills: [],
        }
    },
    beforeMount() {
        this.fetchExperince()
        this.fetchSkill()
    }

}
</script>

<style>

</style>