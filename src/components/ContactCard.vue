<script>
import { ref } from "vue";
import axios from "axios";
import Toast from "../components/UI/Toast.vue";
export default {
  name: "ContactCard",
  props: {},
  components: { Toast },
  data() {
    return {
      name: "",
      email: "",
      message: "",
      showToast: false,
      toastMessage: "",
      toastStatus: "",
      sendClicked: false,
    };
  },
  computed: {
    emailValidator() {
      if (this.email.length == 0 && !this.sendClicked) {
        return "default";
        console.log("aqui");
      }

      if (/(.+)@(.+){2,}.(.+){2,}/.test(this.email)) {
        return "valid";
      } else {
        return "invalid";
      }
    },
    nameValidator() {
      if (this.name.length == 0 && !this.sendClicked) {
        return "default";
      }

      if (this.name.length > 1) {
        return "valid";
      } else {
        return "invalid";
      }
    },
    msgValidator() {
      if (this.message.length == 0 && !this.sendClicked) {
        return "default";
      }

      if (this.message.length > 5) {
        return "textareavalid";
      } else {
        return "textareainvalid";
      }
    },
  },
  methods: {
    onReset() {
      this.name = "";
      this.email = "";
      this.message = "";
    },
    submit() {
      const self = this;
      this.sendClicked = true;
      const { name, email, message } = this;

      this.nameValid = name.length > 0;
      this.emailValid = /(.+)@(.+){2,}.(.+){2,}/.test(email);
      this.msgValid = message.length > 5;

      if (!this.nameValid || !this.emailValid || !this.msgValid) {
        //show toast
        console.log("no se puede enviar");
        return;
      }

      axios
        .post("https://tgonz.work/send", {
          email: email,
          name: name,
          message: message,
        })
        .then(function (response) {
          self.openToast("Email has been sent correctly. Thanks", "success");
        })
        .catch(function (error) {
          console.log(error);
          self.openToast(
            "Sorry for the inconvenience. Server under maintenance. If you still want to contact me you can send me an e-mail to gonzaltomas@gmail.com",
            "error"
          );
        });
    },
    openToast(text, status) {
      console.log(text)
      this.toastMessage = text;
      this.toastStatus = status;
      this.showToast = true;
      setTimeout(() => (this.showToast = false), 3000);
    },
  },
};
</script>

<template>
  <h1>CONTACT ME</h1>
  <transition name="toast">
    <Toast :text="toastMessage" :status="toastStatus" v-if="showToast" />
  </transition>

  <form @submit.prevent="submit" @reset="onReset" class="form">
    <!-- <h2>CONTACT ME</h2> -->
    <p type="Name:">
      <input v-bind:class="nameValidator" v-model="name" placeholder="Your Name" />
    </p>
    <p type="Email:">
      <input
        v-bind:class="emailValidator"
        v-model="email"
        type="email"
        placeholder="email@yourcompany.com"
      />
    </p>
    <p type="Message:">
      <textarea
        v-bind:class="msgValidator"
        v-model="message"
        placeholder="Your Message"
      ></textarea>
    </p>

    <div class="multi-button">
      <button type="submit"><fa icon="road" /> Send Message</button>
    </div>
  </form>
</template>

<style scoped>
h1 {
  text-align: center;
  width: 100%;
  font-size: clamp(1.5em, 5vw, 2.5em);
}

::placeholder {
  font-family: "Poppins", sans-serif;
  color: #78788c;
  font-size: 20px;
}

textarea {
  margin-top: 10px;
  width: 100%;
  height: 150px;
  padding: 10px;
  box-sizing: border-box;
  background: none;
  outline: none;
  resize: none;
  border: 0;
  transition: all 0.3s;
  border: 2px solid #bebed2;
  font-family: "Poppins", sans-serif;
  color: #393e46;
  font-size: 20px;
}
textarea:focus {
  border: 2px solid #00adb5;
}
.form {
  width: 60%;
  height: 40%;

  border-radius: 8px;

  margin: auto;
  padding: 20px 30px;
  max-width: calc(100vw - 40px);
  box-sizing: border-box;
  position: relative;

  -webkit-box-shadow: 18px 17px 104px -24px rgb(0 0 0 / 10%);
  box-shadow: 18px 17px 104px -24px rgb(0 0 0 / 10%);
}

h2 {
  margin: 10px 0;
  padding-bottom: 10px;
  width: 160px;
  color: #78788c;
  border-bottom: 3px solid #78788c;
}

input {
  width: 100%;
  padding: 10px;
  box-sizing: border-box;
  background: none;
  outline: none;
  resize: none;
  border: 0;
  transition: all 0.3s;
  border-bottom: 2px solid #bebed2;
  font-family: "Poppins", sans-serif;
  color: #393e46;
  font-size: 20px;
}

input:focus {
  border-bottom: 2px solid #00adb5;
}

.default {
  border-bottom: 2px solid #bebed2;
}

.valid {
  border-bottom: 2px solid #06c012;
}

.invalid {
  border-bottom: 2px solid #c30303;
}

.textareavalid {
  border: 2px solid #06c012;
}
.textareainvalid {
  border: 2px solid #c30303;
}

p:before {
  content: attr(type);
  display: block;
  margin: 28px 0 0;
  font-size: 14px;
  color: #5a5a5a;
}

button {
  font-size: 2.5vmin;
  padding: 0.5em 1em;
  background: #e6e6e6;
  font-family: "Poppins", sans-serif;
  color: #393e46;
  border: 0px solid #a0aec0;
  margin: 0.1em;
  transition: background 0.2s ease, color 0.2s ease, box-shadow 0.2s ease,
    transform 0.2s ease;
  box-shadow: 0 0 0 #bee3f8;
  transform: translateY(0);

  border-radius: 0.5em 0.5em 0.5em 0.5em;
}

button i {
  color: #a0aec0;
  margin-right: 0.3em;
  transition: all 0.2s ease-out;
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

.multi-button {
  text-align: center !important;
}

.toast-enter-from {
  opacity: 0;
  transform: translateY(-60px);
}
/* .toast-enter-to {
    opacity: 1;
    transform: translateY(0);
  } */
.toast-enter-active {
  transition: all 0.3s ease;
}
/* leave transitions */
/* .toast-leave-from {
    opacity: 1;
    transform: translateY(0);
  } */
.toast-leave-to {
  opacity: 0;
  transform: translateY(-60px);
}
.toast-leave-active {
  transition: all 0.3s ease;
}

@media screen and (max-width: 980px) {
  .form {
    width: 100%;
    height: 100%;
    margin: 0 auto;
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
