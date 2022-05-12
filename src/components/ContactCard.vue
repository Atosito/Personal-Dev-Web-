<script >

export default {
    name: "ContactCard",
    props: {},
    data() {
        return {

        }
    }
}

</script>

<template>
    <form class="form">
        <h2>CONTACT ME</h2>
        <p type="Name:"><input placeholder="Your Name" /></p>
        <p type="Email:"><input type="email" placeholder="email@yourcompany.com" /></p>
        <p type="Message:"><textarea placeholder="Your Message"></textarea></p>
       
            <div class="multi-button"><button >
                <fa icon="road" /> Send Message
            </button> </div>
    </form>

</template>

<style scoped>

::placeholder {
 font-family: 'Poppins', sans-serif;
 color: #78788c;
 font-size: 20px;
}

textarea{
    margin-top: 10px;
     width: 100%;
     height: 150px;
    padding: 10px;
    box-sizing: border-box;
    background: none;
    outline: none;
    resize: none;
    border: 0;
    transition: all .3s;
    border: 2px solid #bebed2
}
textarea:focus {
    border: 2px solid #00ADB5
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
    border-bottom: 3px solid #78788c
}

input {
    width: 100%;
    padding: 10px;
    box-sizing: border-box;
    background: none;
    outline: none;
    resize: none;
    border: 0;
    transition: all .3s;
    border-bottom: 2px solid #bebed2
}

input:focus {
    border-bottom: 2px solid #00ADB5
}

p:before {
    content: attr(type);
    display: block;
    margin: 28px 0 0;
    font-size: 14px;
    color: #5a5a5a
}

button {
    font-size: 2.5vmin;
    padding: .5em 1em;
     background: #e6e6e6;
    font-family: 'Poppins', sans-serif;
    color: #393E46;
    border: 0px solid #A0AEC0;
    margin: .1em;
    transition: background .2s ease, color .2s ease, box-shadow .2s ease, transform .2s ease;
    box-shadow: 0 0 0 #BEE3F8;
    transform: translateY(0);

    border-radius: .5em .5em .5em .5em;
}



button i {
    color: #A0AEC0;
    margin-right: .3em;
    transition: all .2s ease-out;
}



.multi-button:hover button {
    color: #A0AEC0;
}

.multi-button:hover button:hover {
    background: #00ADB5;
    color: #fff;
    box-shadow: 0 0 0.8em 0 rgb(0, 173, 181, .8);
    transform: translateY(-.2em);
}

.multi-button:hover button i {
    color: #CBD5E0;
}

.multi-button:hover button:hover i {
    color: #FED7E2;
    transform: rotate(-10deg);
}

.multi-button{
  text-align: center !important;
}



@media screen and (max-width: 980px) {
 .form{
width: 100%;
height: 100%;
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