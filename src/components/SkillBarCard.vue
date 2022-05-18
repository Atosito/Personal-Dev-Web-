<script >
export default {
    name: "SkillBarCard",
    props: {},
    data() {
        return {
            isActive: false
        }
    },
    created() {
        window.addEventListener("scroll", this.handleScroll);
    },
    destroyed() {
        window.removeEventListener("scroll", this.handleScroll);
    },
    methods: {
        handleScroll(event) {
            this.isActive = true
        },
    },
};
</script>

<template>
    <div class="skill-bars">
        <div class="bar">
            <div class="info">
                <span>NODE.JS</span>
            </div>
            <div class="progress-line nodejs" :class="{ activeBar: isActive }">
                <span></span>
            </div>
        </div>
        <div class="bar">
            <div class="info">
                <span>VUE.JS</span>
            </div>
            <div class="progress-line vuejs" :class="{ activeBar: isActive }">
                <span></span>
            </div>
        </div>
        <div class="bar">
            <div class="info">
                <span>MONGO DB</span>
            </div>
            <div class="progress-line mongo" :class="{ activeBar: isActive }">
                <span></span>
            </div>
        </div>
        <div class="bar">
            <div class="info">
                <span>REACT NATIVE</span>
            </div>
            <div class="progress-line ionic" :class="{ activeBar: isActive }">
                <span></span>
            </div>
        </div>
        <div class="bar">
            <div class="info">
                <span>HTML/CSS</span>
            </div>
            <div class="progress-line htmlcss" :class="{ activeBar: isActive }">
                <span></span>
            </div>
        </div>
        <div class="bar">
            <div class="info">
                <span>IONIC</span>
            </div>
            <div class="progress-line ionic" :class="{ activeBar: isActive }">
                <span></span>
            </div>
        </div>

    </div>
</template>

<style scoped>
.skill-bars {
    width: 100%;
    background-color: white;

}

.skill-bars .bar {
    margin: 20px 0;
}

.skill-bars .bar:first-child {
    margin-top: 0px;
}

.skill-bars .bar .info {
    margin-bottom: 5px;
}

.skill-bars .bar .info span {
    text-transform: uppercase;
    letter-spacing: .2rem;
    font-size: 1rem;
    opacity: 1;
    font-weight: bold;
}


.skill-bars .bar .progress-line {
    height: 10px;
    width: 100%;
    background: #f0f0f0;
    position: relative;

    border-radius: 10px;
    box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05),
        0 1px rgba(255, 255, 255, 0.8);
    transform: scaleX(0);
    transform-origin: left;

}

.activeBar {
    animation: animate 1s cubic-bezier(1, 0, 0.5, 1) forwards;
}



@keyframes animate {
    100% {
        transform: scaleX(1);
    }
}

.bar .progress-line span {
    height: 100%;
    position: absolute;
    border-radius: 10px;

   background-color: var(--special-color);

}

.bar .progress-line span .active {
    transform: scaleX(0);
    transform-origin: left;
    animation: animate 1s 1s cubic-bezier(1, 0, 0.5, 1) forwards;
}

.bar .progress-line.nodejs span {
    width: 90%;
}

.bar .progress-line.mongo span {
    width: 85%;
}

.bar .progress-line.vuejs span {
    width: 80%;
}

.bar .progress-line.ionic span {
    width: 75%;
}

.bar .progress-line.htmlcss span {
    width: 70%;
}

.bar .progress-line.65 span {
    width: 65%;
}

.bar .progress-line.60 span {
    width: 60%;
}

.progress-line span::before {
    position: absolute;
    content: "";
    top: -10px;
    right: 0;
    height: 0;
    width: 0;
    border: 7px solid transparent;
    border-bottom-width: 0px;
    border-right-width: 0px;
    border-top-color: #000;
    opacity: 0;
    animation: showText2 0.5s 1.5s linear forwards;
}

.progress-line span::after {
    position: absolute;
    top: -28px;
    right: 0;
    font-weight: 500;
    background: #000;
    color: #fff;
    padding: 1px 8px;
    font-size: 1rem;
    border-radius: 3px;
    opacity: 0;
    animation: showText2 0.5s 1.5s linear forwards;
}

@keyframes showText2 {
    100% {
        opacity: 1;
    }
}

.progress-line.nodejs span::after {
    content: "90%";
}

.progress-line.css span::after {
    content: "60%";
}

.progress-line.mongo span::after {
    content: "85%";
}

.progress-line.vuejs span::after {
    content: "80%";
}

.progress-line.ionic span::after {
    content: "75%";
}

.progress-line.htmlcss span::after {
    content: "70%";
}
</style>