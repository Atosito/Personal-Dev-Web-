<script>
export default {
  name: "Tutorials",
  props: {},
  data() {
    return {
      openModal: false,
      tutorials: [
        {
          title: "How to get amazon product price",
          modal: false,
          date: "Oct 2020 - Dec 2020",
          text: "Guide to scrap web amazon.com with javascript cheerio.",
          images: [],
          styleObject: {
            "background-color":
              '#8a9192',
          },
          styleImg: {
            height: "600px",
            width: "700px",
            "object-fit":"cover"
          },
          tags: ["Javascript", "Node.js", "Cheerio", "Web-Scraper"],
          buttons: [
            {
              icon: "play",
              url: "https://tgonz.work/hispana",
              text: "Demo",
            },
          ],
        },

      ],
    };
  },
  methods: {
    open(url) {
      window.open(url, "_blank");
    },
  },
  mounted() {
    // Close modal with 'esc' key
  },
};
</script>

<template>
  <h1>TUTORIALS</h1>

  <div class="container">
    <a
      v-for="tuto in tutorials"
      class="card"
      :style="tuto.styleObject"
     
    >

      <div>
        <h2>{{ tuto.title }}</h2>
        <p>{{ tuto.text }}</p>
       <!-- <div class="date">{{ job.date }}</div> -->
        <div class="tags">
          <div v-for="tag in tuto.tags" class="tag">{{ tag }}</div>
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
  border-radius: 0.5em;
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
