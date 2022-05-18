<script>
export default {
  name: "Portfolio",
  props: {},
  data() {
    return {
      jobs: [
        {
          title: "Hispana Obras",
          date: "Oct 2020 - Dec 2020",
          text:
            "The property management admin tool for your real-estate enterprise.",
          imgPath: "./hispana_2.PNG",
          styleObject: {
            "background-image": 'linear-gradient(rgba(105,105,105,0.5), rgba(105,105,105,0.5)), url("./hispana_2.PNG")',
          },
          tags: ["Express.js", "Vue 2.0", "BootstrapVue", "MongoDB"],
        },
        {
          title: "Visiona",
          date: "Nov 2021 - Present",
          text:
            "Hybrid Mobile App to provide a few securities cameras video 24/7 in your device. Also you have a button to call emergency of private security.",
          styleObject: {
            "background-image": 'linear-gradient(rgba(105,105,105,0.5), rgba(105,105,105,0.5)),url("./visionax1.png")',
          },
          imgPath: "./visionax1.png",
          tags: ["Ionic","Angular", "CSS", "HTML", "PHP Laravel", "MySQL"],
        },
        {
          title: "Al Instante",
           date: "Jul 2020 - Present",
          text:
            "Hybrid App Mobile that connects clients with professionals workers. Chat in real time included, and gps tracker.",
          styleObject: {
            "background-image": 'linear-gradient(rgba(105,105,105,0.5), rgba(105,105,105,0.5)),url("./serv_ya_3.png")',
          },
          tags: ["Ionic","Angular", "CSS", "HTML", "PHP Laravel", "MySQL"],
        },
      ],
    };
  },
};
</script>

<template>
  <h1>PORTFOLIO</h1>
  <div class="container">
    <a v-for="job in jobs" class="card" :style="job.styleObject">
      <div>
        <h2>{{ job.title }}</h2>
        <p>{{ job.text }}</p>
        <div class="date">{{job.date}}</div>
        <div class="tags">
          <div v-for="tag in job.tags" class="tag">{{ tag }}</div>
        </div>
      </div>
    </a>
  </div>
</template>

<style scoped>
h1 {
  width: 100%;
  font-size: clamp(1.5em, 5vw, 2.5em);
}



.card-text {
  text-overflow: ellipsis;
  min-height: 175px;
  overflow: auto;
  text-align: start;
}

.card {
 
  text-align: start;
  height: 10em;
  width: 20em;
  font-size: 1.5em;
  color: var(--secondary-color);
  border-radius: 1em;
  padding: 1em;
  margin: 20px;
  display: flex;
  align-items: flex-end;
  background-size: cover;
  border-radius: 19px;
  box-shadow: -1px 15px 30px -12px rgba(50, 50, 50, 0.2);
  transition: all 1s ease;
  position: relative;
  overflow: hidden;
  text-decoration: none;
}

h2 {
  margin: 0;
  font-size: 1.5em;
  line-height: 1.2em;
}

.card p {
  font-size: 0.75em;
  margin-top: 0.5em;
  line-height: 2em;
}

.card .tags {
  display: flex;
  text-align: center;
}

.card .tags .tag {
  font-size: 0.75em;
  background: rgba(255, 255, 255, 0.5);
  border-radius: 0.3rem;
  padding: 0 0.5em;
  margin-right: 0.5em;
  line-height: 1.5em;
  transition: all, 0.5;
}

.card:hover .tags .tag {
  background: var(--secondary-color);
  color: white;
}

.card .date {
  position: absolute;
  top: 0;
  right: 0;
  font-size: 0.75em;
  padding: 1em;
  line-height: 1em;
  opacity: 1;
}

.card:before,
.card:after {
  content: "";
  transform: scale(0);
  transform-origin: top left;
  border-radius: 50%;
  position: absolute;
  left: -50%;
  top: -50%;
  z-index: -5;
  transition: all, 0.5;
  transition-timing-function: ease-in-out;
}

.card:before {
  background: #ddd;
  width: 250%;
  height: 250%;
}

.card:after {
  background: white;
  width: 200%;
  height: 200%;
}


.card:hover {
  color: var(--secondary-color);
  background-image: none !important;
}


.card:hover:before,
.card:hover:after {
  transform: scale(1);
   background-image: none !important;
}

.container {
  justify-content: center;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  width: 90vw;
  margin: 0 auto;
}

@media screen and (max-width: 980px) {
  .serviceCard {
    flex: 1 1 24%;
    padding: 2em;
    margin-bottom: 1.5em;
  }
}
</style>
