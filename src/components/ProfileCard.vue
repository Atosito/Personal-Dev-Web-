<script setup>
import SkillBarCard from './SkillBarCard.vue'


</script>

<template>
    <h1>ABOUT ME</h1>
    <div class="container">
        <img src="/profile.jpg" class="photo">
        <p class="card-text">I am a highly competent mobile and web application software developer with three years'
            experience
            developing. I have proven expertise in building social media apps. I am currently seeking long-term
            contract
            positions which will allow me to further improve my project management skills. When I'm not coding,
            you'll
            find me playing sports.</p>


        <div class="personalInfo">
            <h3>PROFILE</h3>
            <ul class="info">
                <li><strong>FULLNAME:</strong>
                    <span>Tomás Gonzalez</span>
                </li>
                <li><strong>BIRTH DATE:</strong>
                    <span>17/06/1994</span>
                </li>
                <li><strong>JOB:</strong>
                    <span>Freelance. Fullstack-Developer</span>
                </li>
                <li><strong>LOCATION:</strong>
                    <span>Buenos Aires, Argentina.</span>
                </li>
                <li><strong>WEBSITE:</strong>
                    <span>www.tgonz.work</span>
                </li>
                <li><strong>EMAIL:</strong>
                    <span>gonzaltomas@gmail.com</span>
                </li>
            </ul>
        </div>
        <div class="personalInfo">
            <h3>SKILLS</h3>
            <SkillBarCard></SkillBarCard>
        </div>
    </div>

</template>

<style scoped>
.container {
    display: flex;  
    flex-wrap: wrap;
    justify-content: center;
    width: 70%;
    margin: 0 auto;
}

.card-text {
    text-overflow: ellipsis;
    overflow: auto;
    width: 58%;
}

.photo {
    display: flex;
    justify-content: flex-end;
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
    margin: auto 0;
}


.info {

    margin-left: 0 !important;
    padding-inline-start: 0;
    list-style: none;

}

@media screen and (max-width: 1000px) {


    .card-text {
        width: 100%;
    }
}

span {
    display: block;
    color: #888888;
    font-size: 1rem;
    line-height: 1;
    margin-top: -10px;
}

h3 {
    font-size: 1rem;
}

strong {

    text-transform: uppercase;
    letter-spacing: .2rem;
    font-size: 1rem;
    line-height: 3rem;
}

h1 {
    width: 100%;
    font-size: clamp(1.5em, 5vw, 2.5em);
}

.personalInfo {
    width: 50%;
    text-align: start;
    list-style: none;
}

p {
    padding-left: 20px;
    width: 50%;
    text-align: start;
    font-size: 1rem;

}



@media screen and (max-width: 1000px) {}

@media screen and (max-width: 780px) {
    .personalInfo {
        width: 100%;
    }
}

@media screen and (max-width: 380px) {
    .card-text {
        height: 200px;
    }
}
</style>