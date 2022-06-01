<script>
export default {
  name: "Portfolio",
  props: {},
  data() {
    return {
      openModal: false,

      jobs: [
        {
          title: "Hispana Obras",
          modal: false,
          date: "Oct 2020 - Dec 2020",
          text: "The property management admin tool for your real-estate enterprise.",
          images: ["./hispana_1.PNG", "./hispana_2.PNG"],
          styleObject: {
            "background-image":
              'linear-gradient(rgba(105,105,105,0.5), rgba(105,105,105,0.5)), url("./hispana_2.PNG")',
          },
          styleImg: {
            height: "600px",
            width: "700px",
          },
          tags: ["Express.js", "Vue 2.0", "BootstrapVue", "MongoDB"],
          buttons: [{
            icon:"play",
            url:"https://tgonz.work/hispana",
            text:"Demo"
          }]
        },
        {
          title: "Visiona",
          date: "Nov 2021 - Present",
          modal: false,
          text:
            "Hybrid Mobile App to provide a few securities cameras video 24/7 in your device. Also you have a button to call emergency of private security.",
          styleObject: {
            "background-image":
              'linear-gradient(rgba(105,105,105,0.5), rgba(105,105,105,0.5)),url("./visionax1.png")',
          },
          styleImg: {
            height: "600px",
            width: "400px",
          },
          images: ["./visiona_1.PNG", "./visionax1.png", "./visiona_3.PNG"],
          tags: ["Ionic", "Angular", "CSS", "HTML", "PHP Laravel", "MySQL"],
           buttons: [{
            icon:"store",
            url:"http://visiona.app.com/",
            text:"Apple Store"
          },{
            icon:"store",
            url:"https://play.google.com/store/apps/details?id=visiona.app",
            text:"Play Store"
          },]
        },
        {
          title: "Al Instante",
          date: "Jul 2020 - Present",
          modal: false,
          text:
            "Hybrid App Mobile that connects clients with professionals workers. Chat in real time included, and gps tracker.",
          styleObject: {
            "background-image":
              'linear-gradient(rgba(105,105,105,0.5), rgba(105,105,105,0.5)),url("./serv_ya_3.png")',
          },
          styleImg: {
            height: "600px",
            width: "400px",
          },
          images: ["./serv_ya_1.png", "./serv_ya_2.png", "./serv_ya_3.png"],
          tags: ["Ionic", "Angular", "CSS", "HTML", "PHP Laravel", "MySQL"],
        },
      ],
    };
  },
  methods: {
    closeModal() {
      this.jobs.forEach((job) => {
        job.modal = false;
      });
    },
    open(url) {
      window.open(url, "_blank");
    },
  },
  mounted() {
    // Close modal with 'esc' key
    document.addEventListener("keydown", (e) => {
      if (e.keyCode == 27) {
        this.jobs.forEach((job) => {
          job.modal = false;
        });
      }
    });
  },
};
</script>

<template>
  <h1>PORTFOLIO</h1>

  <div class="container">
    <a
      v-for="job in jobs"
      class="card"
      @click="job.modal = !job.modal"
      :style="job.styleObject"
    >
      <Teleport v-if="job.modal" to="#modals">
        <transition name="fade" appear>
          <dialog open class="mobileModal">
            <div class="modalContainer">
              <a @click="closeModal" class="close"></a>
              <img v-for="img in job.images" :style="job.styleImg" :src="img" />
            </div>
            <div class="multi-button">
              <button v-for="btn in job.buttons" @click="open(btn.url)"><fa :icon="btn.icon" /> <span> {{btn.text}}</span></button>
            </div>
          </dialog>
        </transition>
      </Teleport>

      <div>
        <h2>{{ job.title }}</h2>
        <p>{{ job.text }}</p>
        <div class="date">{{ job.date }}</div>
        <div class="tags">
          <div v-for="tag in job.tags" class="tag">{{ tag }}</div>
        </div>
      </div>
    </a>
  </div>
</template>

<style scoped>
button {
  font-size: 20px;
  padding: 0.5em 1em;
  background: #fff;
  font-family: "Poppins", sans-serif;
  color: var(--terciary-color);
  border: 0px solid #a0aec0;
  margin: 0.1em;
  transition: background 0.2s ease, color 0.2s ease, box-shadow 0.2s ease,
    transform 0.2s ease;
  box-shadow: 0 0 0 #bee3f8;
  transform: translateY(0);
   border-radius: 0.5em ;
}


button i {
  color: #a0aec0;
  margin-right: 0.3em;
  transition: all 0.2s ease-out;
}

.multi-button {
  text-align: center;
  width: 100%;
}

.multi-button:hover button {
  color: #a0aec0;
}

.multi-button:hover button:hover {
  background-color: var(--special-color);
  color: var(--primary-color);
  box-shadow: 0 0 0.8em 0 rgb(0, 173, 181, 0.8);
  transform: translateY(-0.2em);
}

.multi-button:hover button i {
  color: #cbd5e0;
}

.multi-button:hover button:hover i {
  color: #fed7e2;
  transform: rotate(-10deg);
}
h1 {
  width: 100%;
  font-size: clamp(1.5em, 5vw, 2.5em);
}

img {
  margin: 5px;
  border-radius: 19px;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s linear;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.modalContainer {
  margin: auto;
  justify-content: center;
  align-items: center;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.mobileModal {
  border: 0;
  padding: 0;
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  justify-content: center;
  align-items: center;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  background-color: rgba(0, 0, 0, 0.4); /* Black w/ opacity */
}
.card-text {
  text-overflow: ellipsis;
  min-height: 175px;
  overflow: auto;
  text-align: start;
}
.close {
  position: fixed;
  right: 32px;
  top: 32px;
  width: 32px;
  height: 32px;
  opacity: 0.6;
}
.close:hover {
  opacity: 1;
  cursor: pointer;
}
.close:before,
.close:after {
  position: absolute;
  left: 15px;
  content: " ";
  height: 33px;
  width: 2px;
  background-color: var(--special-color);
}
.close:before {
  transform: rotate(45deg);
}
.close:after {
  transform: rotate(-45deg);
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
  cursor: pointer;
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

dialog::backdrop {
  /* position: fixed;
  inset: 0;
  background: #0006; */

  backdrop-filter: blur(2px);
}

@media screen and (max-width: 980px) {
  .serviceCard {
    flex: 1 1 24%;
    padding: 2em;
    margin-bottom: 1.5em;
  }
}
</style>
