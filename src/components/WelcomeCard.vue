<script>
export default {
  name: "WelcomeCard",
  props: {},
  data() {
    return {};
  },
  computed: {},
  methods: {
    goto(num) {
      window.scrollTo({
        top: window.innerHeight * num,
        left: 0,
        behavior: "smooth",
      });
    },
    open(url) {
      window.open(url, "_blank");
    },
    copy(text) {
      navigator.clipboard.writeText(text);
      console.log("copied");
    },
  },
};
</script>

<template>
  <div class="welcomeCard">
    <h1>Hello, World!</h1>
    <h2>I'm Tomás Gonzalez</h2>
    <h3>| FullStack-Developer | Mobile-Developer |</h3>
    <div class="multi-button">
      <button><fa icon="road" /> <span> Experiencie </span></button>
      <button @click="goto(1)"><fa icon="user" /><span> Profile</span></button>
      <!-- <button>
        <fa icon="school" /> Education
      </button> -->
      <button><fa icon="suitcase" /> <span>Portfolio</span></button>
      <button @click="goto(2)"><fa icon="brain" /><span> Services</span></button>
      <button @click="goto(3)"><fa icon="envelope" /><span> Contact</span></button>
    </div>
  </div>
  <div class="social-links">
    <div class="social-btn flex-center" slot="" id="discord" @click="copy('tomi.g#9364')">
      <svg
        width="24"
        height="24"
        viewBox="0 -28.5 256 256"
        version="1.1"
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        preserveAspectRatio="xMidYMid"
      >
        <g>
          <path
            d="M216.856339,16.5966031 C200.285002,8.84328665 182.566144,3.2084988 164.041564,0 C161.766523,4.11318106 159.108624,9.64549908 157.276099,14.0464379 C137.583995,11.0849896 118.072967,11.0849896 98.7430163,14.0464379 C96.9108417,9.64549908 94.1925838,4.11318106 91.8971895,0 C73.3526068,3.2084988 55.6133949,8.86399117 39.0420583,16.6376612 C5.61752293,67.146514 -3.4433191,116.400813 1.08711069,164.955721 C23.2560196,181.510915 44.7403634,191.567697 65.8621325,198.148576 C71.0772151,190.971126 75.7283628,183.341335 79.7352139,175.300261 C72.104019,172.400575 64.7949724,168.822202 57.8887866,164.667963 C59.7209612,163.310589 61.5131304,161.891452 63.2445898,160.431257 C105.36741,180.133187 151.134928,180.133187 192.754523,160.431257 C194.506336,161.891452 196.298154,163.310589 198.110326,164.667963 C191.183787,168.842556 183.854737,172.420929 176.223542,175.320965 C180.230393,183.341335 184.861538,190.991831 190.096624,198.16893 C211.238746,191.588051 232.743023,181.531619 254.911949,164.955721 C260.227747,108.668201 245.831087,59.8662432 216.856339,16.5966031 Z M85.4738752,135.09489 C72.8290281,135.09489 62.4592217,123.290155 62.4592217,108.914901 C62.4592217,94.5396472 72.607595,82.7145587 85.4738752,82.7145587 C98.3405064,82.7145587 108.709962,94.5189427 108.488529,108.914901 C108.508531,123.290155 98.3405064,135.09489 85.4738752,135.09489 Z M170.525237,135.09489 C157.88039,135.09489 147.510584,123.290155 147.510584,108.914901 C147.510584,94.5396472 157.658606,82.7145587 170.525237,82.7145587 C183.391518,82.7145587 193.761324,94.5189427 193.539891,108.914901 C193.539891,123.290155 183.391518,135.09489 170.525237,135.09489 Z"
            fill="#5865F2"
            fill-rule="nonzero"
          ></path>
        </g></svg
      ><span>tomi.g#9364</span>
    </div>
    <div
      class="social-btn flex-center"
      slot=""
      id="twitter"
      @click="open('https://twitter.com/toomi17')"
    >
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
        <path
          d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"
        /></svg
      ><span>@toomi17</span>
    </div>

    <div
      class="social-btn flex-center"
      id="linkedin"
      @click="open('https://www.linkedin.com/in/tomig/')"
    >
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
        <path
          d="M4.98 3.5c0 1.381-1.11 2.5-2.48 2.5s-2.48-1.119-2.48-2.5c0-1.38 1.11-2.5 2.48-2.5s2.48 1.12 2.48 2.5zm.02 4.5h-5v16h5v-16zm7.982 0h-4.968v16h4.969v-8.399c0-4.67 6.029-5.052 6.029 0v8.399h4.988v-10.131c0-7.88-8.922-7.593-11.018-3.714v-2.155z"
        /></svg
      ><span>in/tomig</span>
    </div>

    <div
      class="social-btn flex-center"
      id="github"
      @click="open('https://github.com/Atosito')"
    >
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
        <path
          d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
        /></svg
      ><span>Atosito</span>
    </div>
    <div
      class="social-btn flex-center"
      id="github"
      @click="open('https://mail.google.com/mail/?view=cm&fs=1&tf=1&to=gonzaltomas@gmail.com')"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        aria-label="Gmail"
        role="img"
        viewBox="0 0 512 512"
      >
        <rect width="24" height="24" rx="15%" fill="#fff" />
        <path d="M158 391v-142l-82-63V361q0 30 30 30" fill="#4285f4" />
        <path d="M 154 248l102 77l102-77v-98l-102 77l-102-77" fill="#ea4335" />
        <path d="M354 391v-142l82-63V361q0 30-30 30" fill="#34a853" />
        <path d="M76 188l82 63v-98l-30-23c-27-21-52 0-52 26" fill="#c5221f" />
        <path d="M436 188l-82 63v-98l30-23c27-21 52 0 52 26" fill="#fbbc04" /></svg
      ><span>gonzaltomas</span>
    </div>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Lora&family=Poppins:wght@500;700&display=swap");

.welcomeCard {
  margin: auto;
}

h1 {
  color: #00adb5;
  font-family: "Poppins", sans-serif;
  font-size: 2em;
  line-height: 1.565;
  margin-bottom: 0;
  text-transform: uppercase;
  letter-spacing: 0.3rem;
  text-shadow: 0 0 6px rgb(0 0 0 / 20%);
}

h2 {
  color: #eeeeee;
  font-family: "Poppins", sans-serif;
  font-size: 3em;
  line-height: 1.071;
  max-width: 900px;
  margin-top: 0;
  margin-bottom: 0.6rem;
  margin-left: auto;
  margin-right: auto;
  text-shadow: 0 0 20px rgb(0 0 0 / 50%);
}

h3 {
  font-family: "Lora", serif;

  font-size: 0.9rem;
  line-height: 2.4rem;
  text-transform: uppercase;
  letter-spacing: 0.2rem;
  color: #d3d3d3;
  text-shadow: 0 0 6px rgb(0 0 0 / 20%);
}

button {
  font-size: 20px;
  padding: 0.5em 1em;
  background: #fff;
  font-family: "Poppins", sans-serif;
  color: #393e46;
  border: 0px solid #a0aec0;
  margin: 0.1em;
  transition: background 0.2s ease, color 0.2s ease, box-shadow 0.2s ease,
    transform 0.2s ease;
  box-shadow: 0 0 0 #bee3f8;
  transform: translateY(0);
}

button:first-of-type {
  border-radius: 0.5em 0 0 0.5em;
}

button:last-of-type {
  border-radius: 0 0.5em 0.5em 0;
}

button i {
  color: #a0aec0;
  margin-right: 0.3em;
  transition: all 0.2s ease-out;
}

.multi-button {
  margin: auto;
}

.multi-button:hover button {
  color: #a0aec0;
}

.multi-button:hover button:hover {
  background: #00adb5;
  color: #fff;
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

.flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}

.social-links {
  /* display: flex;
    justify-content: center;
    align-self: flex-end;
    margin: 0 auto !important; */
  position: fixed;
  top: 50%;
  -webkit-transform: translateY(-50%);
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
}

.social-btn {
  cursor: pointer;
  height: 50px;
  width: 50px;
  color: #333;
  border-radius: 10px;
  box-shadow: 0px 10px 10px rgba(0, 0, 0, 0.1);
  background: white;
  margin: 5px;
  transition: 1s;
}

.social-btn span {
  width: 0px;
  overflow: hidden;
  transition: 1s;
  text-align: center;
}

.social-btn:hover {
  width: 170px;
  border-radius: 5px;
}

.social-btn:hover span {
  padding: 2px;
  width: max-content;
}

#twitter svg {
  fill: #1da1f2;
}

#linkedin svg {
  fill: #0e76a8;
}

#github {
  fill: #333;
}

@media screen and (max-width: 980px) {
  .multi-button {
    width: 90%;
  }

  button span {
    font-size: 0;
  }
  button {
    font-size: 24px;
  }

  .social-links {
    all: initial;
    display: flex;
    justify-content: center;
    align-self: center;
    margin: 0 auto !important;
    position: fixed;
  }
}
</style>
