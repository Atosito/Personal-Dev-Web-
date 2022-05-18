<script>
export default {
  name: "ServiceCard",
  props: {},
  data() {
    return {
      services: [
        {
          title: "Back-End",
          text:
            "I build APIs that will facilitate communication between your web client and your database. User management, stock management, real-time chat integration.",
          imgPath: "./api.png",
          list: ["Socket.io", "Express.js", "PHP Laravel", "Mongo DB - SQL"],
        },
        {
          title: "Fullstack Development",
          text:
            "I offer full development of your step into the online world. If you want to upload your business to the cloud or if you have an innovative idea.",
          imgPath: "./web.png",
          list: ["HTML5/CSS", "Vue.js", "Angular"],
        },
        {
          title: "Hybrid Mobile App",
          text:
            "I offer practical solutions for the creation of mobile applications that adapt to iOS and Android. I develop in javascript/typescript based environments like Ionic or React Native.",
          imgPath: "./mobile.png",
          list: ["Ionic Angular v5", "React Native"],
        },
      ],
    };
  },
};
</script>

<template>
  <h1>SERVICES</h1>
  <div class="container">
    <div v-for="service in services" class="serviceCard">
      <img :src="service.imgPath" class="img" />
      <h2>{{ service.title }}</h2>
      <p class="card-text">{{ service.text }}</p>
      <ul style="text-align: start">
        <li v-for="item in service.list">{{ item }}</li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
h1 {
  width: 100%;
  font-size: clamp(1.5em, 5vw, 2.5em);
}

h2 {
  font-size: clamp(1em, 5vw, 1em);
}

.card-text {
  text-overflow: ellipsis;
  min-height: 175px;
  overflow: auto;
  text-align: start;
}

.container {
  justify-content: center;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  width: 90vw;
  margin: 0 auto;
}

.serviceCard {
  flex: 0 1 24%;
  padding: 2em;
  margin-bottom: 1.5em;
  box-shadow: -1px 15px 30px -12px rgba(50, 50, 50, 0.2);
}

.img {
  display: flex;
  justify-content: flex-end;
  width: 150px;
  height: 150px;
  border-radius: 50%;
  display: block;
  margin: auto;
  object-fit: cover;
}

ul {
  display: block;
  margin-left: -10px;
}

ul li {
  display: block;
  position: relative;
}

ul li:not(:last-child) {
  margin-bottom: 16px;
}

ul li:before {
  content: "";
  position: absolute;
  top: 1.2em;
  left: -30px;
  margin-top: -0.9em;
  background-color: var(--special-color);
  height: 12px;
  width: 12px;
  border-radius: 50%;
}

@media screen and (max-width: 980px) {
  .serviceCard {
    flex: 1 1 24%;
    padding: 2em;
    margin-bottom: 1.5em;
  }
}
</style>
