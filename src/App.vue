<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import WelcomeCard from './components/WelcomeCard.vue'
import ProfileCard from './components/ProfileCard.vue'
import ServiceCard from './components/ServiceCard.vue'
import ContactCard from './components/ContactCard.vue'



</script>

<template>
  <div class="flex-container">
    <section id="intro">
      <WelcomeCard @scrollto="goto"></WelcomeCard>
    </section>
    <section id="profile">
      <ProfileCard></ProfileCard>
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



#app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;

}

/* #contact {
    width: 100vw;
  min-height: 100vh;

  display: table;
  position: relative;
  margin:0
}
#profile {
  width: 100vw;
  min-height: 100vh;

  display: table;
  position: relative;
  text-align: center;
}

#services {
  width: 100vw;
  min-height: 100vh;

  display: table;
  position: relative;
  text-align: center;
  
}

#intro {

  background: url("/background3.jpg") no-repeat center bottom;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  background-size: cover;
  background-attachment: fixed;
  width: 100vw;
  min-height: 100vh;
  display: table;
  position: relative;
  text-align: center;


}



/* html{
   background: url("/background.jpg") no-repeat center center fixed ;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
} */
body {
  margin: 0 !important;
}
</style>
