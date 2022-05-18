<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import WelcomeCard from './components/WelcomeCard.vue'
import ProfileCard from './components/ProfileCard.vue'
import ServiceCard from './components/ServiceCard.vue'
import ContactCard from './components/ContactCard.vue'
import PortfolioCard from './components/PortfolioCard.vue'



</script>

<template>
  <div class="flex-container">
    <section id="intro">
      <WelcomeCard @scrollto="goto"></WelcomeCard>
    </section>
    <section id="profile">
      <ProfileCard></ProfileCard>
    </section>
     <section id="portfolio">
      <PortfolioCard></PortfolioCard>
    </section>
    <section id="services">
      <ServiceCard></ServiceCard>
    </section>

     <section id="contact">
      <ContactCard></ContactCard>
    </section>
 
  </div>

</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lora&family=Poppins:wght@500;700&display=swap');



element {
    --primary-color: #EEEEEE;
    --secondary-color: #222831;
    --terciary-color: #393E46;
    --special-color: #00ADB5;
  }

.flex-container{
    display: flex;
    flex-direction: column;
    width: 100%;
}
section {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

#intro {
  background: url("/background3.jpg") no-repeat center bottom;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  background-size: cover;
  background-attachment: fixed;
  text-align: center;
}

#profile{
   text-align: center;
}
#services {
  text-align: center;

}
#portfolio {
  text-align: center;

}



#app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: var(--secondary-color);

}

body {
  margin: 0 !important;
}
</style>
