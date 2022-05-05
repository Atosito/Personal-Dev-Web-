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
    <form class="form multi-button">
        <h2>CONTACT US</h2>
        <p type="Name:"><input placeholder="dsa" /></p>
        <p type="Email:"><input placeholder="Let us know how to contact you back" /></p>
        <p type="Message:"><input placeholder="What would you like to tell us" /></p>
       
            <button class="multi-button">
                <fa icon="road" /> Send Message
            </button>
    
        <div>
            <span class="fa fa-phone"></span>001 1023 567
            <span class="fa fa-envelope-o"></span> contact@company.com
        </div>
    </form>

</template>

<style scoped>
.form {
    width: 340px;
    height: 440px;
    background: #e6e6e6;
    border-radius: 8px;
    box-shadow: 0 0 40px -10px #000;
    margin: calc(50vh - 220px) auto;
    padding: 20px 30px;
    max-width: calc(100vw - 40px);
    box-sizing: border-box;
    position: relative
}

h2 {
    margin: 10px 0;
    padding-bottom: 10px;
    width: 180px;
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
    border-bottom: 2px solid #78788c
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
    background: #fff;
    font-family: 'Poppins', sans-serif;
    color: #393E46;
    border: 0px solid #A0AEC0;
    margin: .1em;
    transition: background .2s ease, color .2s ease, box-shadow .2s ease, transform .2s ease;
    box-shadow: 0 0 0 #BEE3F8;
    transform: translateY(0);
}

button:first-of-type {
    border-radius: .5em 0 0 .5em;
}

button:last-of-type {
    border-radius: 0 .5em .5em 0;
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


div {
    content: 'Hi';
    position: absolute;
    bottom: -15px;
    right: -20px;
    background: #50505a;
    color: #fff;
    width: 320px;
    padding: 16px 4px 16px 0;
    border-radius: 6px;
    font-size: 13px;
    box-shadow: 10px 10px 40px -14px #000
}

span {
    margin: 0 5px 0 15px
}
</style>