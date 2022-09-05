<template>
    <div id="app" class="campaign-results-animation">
        <div class="campaign-results-animation__hospitals">
            <div
                v-for="hospital in hospitals"
                :key="hospital.index"
                :class="[hospital.title, hospital.class]"
            ></div>
        </div>
        <div class="btn-wrapper">
            <button class="left" @click="goLeft">left</button>
            <button class="right" @click="goRight">right</button>
        </div>
    </div>
</template>

<script>
import anime from 'animejs/lib/anime.es.js';

export default {
    name: 'App',
    data() {
        return {
            default: '',
            right: '',
            left: '',
            isFirst: 0,
            hospitals: [
                { index: 0, class: 'default', title: 'children' }, // left
                { index: 1, class: 'right', title: 'maternity' }, // def
                { index: 2, class: 'left', title: 'onco' }, // right
                // { index: 3, class: 'on-hidden', title: 'city' }
            ],
            defaultHospital: 0, // children
            right: {
                '.centered': {
                    // targets: '.centered',
                    // rotate: 30,
                    // translateX: '22%',
                    // translateY: '-12%',
                    // scale: [1, .8],
                    // easing: 'easeOutExpo',

                    // targets: '.on-right',
                    // opacity: [1, 0],
                    // scale: [.8, .8],
                    // rotate: 35,
                    // translateX: '40%',
                    // translateY: '-10%',
                    // easing: 'easeOutExpo',

                    targets: '.on-left',
                    scale: [.8, 1],
                    rotate: 24,
                    translateX: '22%',
                    translateY: '-13%',
                    easing: 'easeOutExpo',
                },
                '.on-right': {
                    // targets: '.on-left',
                    // opacity: [1, 0],
                    // scale: [.8, .8],
                    // rotate: 35,
                    // translateX: '40%',
                    // translateY: '-10%',
                    // easing: 'easeOutExpo',

                    targets: '.centered',
                    rotate: 30,
                    translateX: '22%',
                    translateY: '-12%',
                    scale: [1, .8],
                    easing: 'easeOutExpo',
                },
                '.on-left': {
                    // targets: '.on-left',
                    // scale: [.8, 1],
                    // rotate: 24,
                    // translateX: '22%',
                    // translateY: '-13%',
                    // easing: 'easeOutExpo',
                    // targets: '.centered',
                    // rotate: 30,
                    // translateX: '22%',
                    // translateY: '-12%',
                    // scale: [1, .8],
                    // easing: 'easeOutExpo',

                    targets: '.on-right',
                    // opacity: [1, 0],
                    // scale: [.8, .8],
                    // rotate: 35,
                    // translateX: '40%',
                    // translateY: '-10%',
                    // easing: 'easeOutExpo',

                    opacity: [1, 0],
                    scale: [.8, .8],
                    rotate: 35,
                    translateX: '40%',
                    translateY: '-10%',
                    easing: 'easeOutExpo',
                },
                '.on-hidden': {

                },
            },
            left: {
                '.centered': {

                },
                '.on-right': {

                },
                '.on-left': {

                },
                '.on-hidden': {

                },
            }
        }
    },
    methods: {
        goRight() {
            // const index = this.hospitals.findIndex((el) => el.index === this.defaultHospital)

            // if (index === 2) {
            //     this.defaultHospital = 0
            // } else {
            //     this.defaultHospital += 1
            // }

            // this.assignClass('right')

            // const right = this.defaultHospital + 1 > 2 ? 0 : this.defaultHospital + 1
            // const left = this.defaultHospital - 1 < 0 ? 2 : this.defaultHospital - 1

            // if (this.isFirst > 0) {
            //     this.hospitals[this.defaultHospital].title = this.hospitals[right].title
            //     this.hospitals[right].title = this.hospitals[left].title
            //     this.hospitals[left].title = this.hospitals[this.defaultHospital].title
            // }

            // this.isFirst = 1



            // this.default = document.querySelector(`.${this.hospitals[this.defaultHospital].title}`)
            // this.right = document.querySelector(`.${this.hospitals[right].title}`)
            // this.left = document.querySelector(`.${this.hospitals[left].title}`)
            // const defaultEl = document.querySelector(`.${this.hospitals[this.defaultHospital].title}`)
            // const rightEl = document.querySelector(`.${this.hospitals[right].title}`)
            // const leftEl = document.querySelector(`.${this.hospitals[left].title}`)

            // document.querySelector(`.${this.hospitals[this.defaultHospital].title}`).style.transform = "unset"
            // document.querySelector(`.${this.hospitals[right].title}`).style.transform = "unset"
            // document.querySelector(`.${this.hospitals[left].title}`).style.transform = "unset"

            // const elements = ['default', 'right', 'left'];
            // elements.forEach((directionClass) => {
            //     anime(this[direction][directionClass])
            // })
            console.log(this.defaultHospital, 'this.defaultHospital before');

            if (this.defaultHospital === 1) {
                // const right = this.right
                // const left = this.left
                // const defaultEl = this.default

                // this.default = '.children'
                // this.right = '.onco'
                // this.left = '.maternity'

                // this.hospitals[this.defaultHospital].title =
                // this.hospitals[right].title = this.hospitals[left].title
                // this.hospitals[left].title = this.hospitals[this.defaultHospital].title
                anime({
                    targets: '.onco',
                    scale: [.8, 1],
                    rotate: -27,
                    translateX: '-21%',
                    translateY: '-6%',
                    easing: 'easeOutExpo',
                    direction: 'forward'
                })

                anime({
                    targets: '.children',
                    rotate: 25,
                    translateX: '21%',
                    translateY: '-9%',
                    scale: [1, .8],
                    easing: 'easeOutExpo',
                })

                anime({
                    targets: '.maternity',
                    keyframes: [
                        {
                            scale: [.8, .8],
                            opacity: [1, 0],
                            rotate: 35,
                            translateX: '40%',
                            translateY: '-10%',
                        },
                        {
                            scale: [.8, .8],
                            opacity: [0, 1],
                            rotate: -51,
                            translateX: '-43%',
                            translateY: '-52%',
                        },
                    ],
                    // scale: [.8, .8],
                    // rotate: 35,
                    // translateX: '40%',
                    // translateY: '-10%',
                    easing: 'easeOutExpo',
                })

                this.defaultHospital += 1

                document.querySelector(`.maternity`).style.transform = "none"
                document.querySelector(`.onco`).style.transform = "none"
                document.querySelector(`.children`).style.transform = "none"
            }


            if (this.defaultHospital === 0) {

                const right = this.defaultHospital + 1 > 2 ? 0 : this.defaultHospital + 1
                const left = this.defaultHospital - 1 < 0 ? 2 : this.defaultHospital - 1

                const defaultEl = `.${this.hospitals[this.defaultHospital].title}`
                const rightEl = `.${this.hospitals[right].title}`
                const leftEl = `.${this.hospitals[left].title}`

                anime({
                    targets: defaultEl,
                    scale: [.8, 1],
                    rotate: 24,
                    translateX: '22%',
                    translateY: '-12%',
                    easing: 'easeOutExpo',
                    direction: 'forward'
                })

                anime({
                    targets: rightEl,
                    rotate: 25,
                    translateX: '21%',
                    translateY: '-9%',
                    scale: [1, .8],
                    easing: 'easeOutExpo',
                })

                anime({
                    targets: leftEl,
                    keyframes: [
                        {
                            scale: [.8, .8],
                            opacity: [1, 0],
                            rotate: 35,
                            translateX: '40%',
                            translateY: '-10%',
                        },
                        {
                            scale: [.8, .8],
                            opacity: [0, 1],
                            rotate: -51,
                            translateX: '-43%',
                            translateY: '-52%',
                        },
                    ],
                    // scale: [.8, .8],
                    // rotate: 35,
                    // translateX: '40%',
                    // translateY: '-10%',
                    easing: 'easeOutExpo',
                })

                this.defaultHospital += 1

                document.querySelector(`.maternity`).style.transform = "none"
                document.querySelector(`.onco`).style.transform = "none"
                document.querySelector(`.children`).style.transform = "none"
            }



            // const prev = this.hospitals[left].title
            // const current = this.hospitals[this.defaultHospital].title
            // const next = this.hospitals[right].title


            // this.hospitals[this.defaultHospital].title = this.hospitals[right].title
            // this.hospitals[right].title = this.hospitals[left].title
            // this.hospitals[left].title = this.hospitals[this.defaultHospital].title

            // const index = this.hospitals.findIndex((el) => el.index === this.defaultHospital)

            // if (this.isFirst > 0) {
            //     if (index === 2) {
            //         this.defaultHospital = 0
            //     } else {
            //         this.defaultHospital += 1
            //     }
            // }

            // this.isFirst = 1









            // document.querySelector(`.${this.hospitals[this.defaultHospital].title}`).style.transform = "initial"
            // document.querySelector(`.${this.hospitals[right].title}`).style.transform = "initial"
            // document.querySelector(`.${this.hospitals[left].title}`).style.transform = "initial"


            // console.log(this.defaultHospital, 'def hos');



        },
        goLeft() {
            const index = this.hospitals.findIndex((el) => el.index === this.defaultHospital)

            if (index === 0) {
                this.defaultHospital = 2
            } else {
                this.defaultHospital -= 1
            }

            this.assignClass('left')
        },
        assignClass(direction) {
            const directions = ['.centered', '.on-right', '.on-left']

            directions.forEach((directionClass) => {
                anime(this[direction][directionClass])
            })

            // const right = this.defaultHospital + 1 > 2 ? 0 : this.defaultHospital + 1
            // const left = this.defaultHospital - 1 < 0 ? 2 : this.defaultHospital - 1

            // const indexes = [0, 1, 2]
            // const hospitalIndexes = [right, left, this.defaultHospital];

            // let hidden
            // indexes.forEach(element => { if (!hospitalIndexes.includes(element)) hidden = element });

            // const onRight = '.' + this.hospitals[this.defaultHospital].title
            // const onLeft = '.' + this.hospitals[left].title
            // const centered = '.' + this.hospitals[right].title

            // console.log();

            // const onLeft = '.' + this.hospitals[this.defaultHospital].title
            // const centered = '.' + this.hospitals[right].title
            // const onRight = '.' + this.hospitals[left].title

            console.log(onRight, onLeft, centered, 'mater, onco, childred ');
            // const onHidden = '.' + this.hospitals[hidden].title


            // console.log(this.hospitals[this.defaultHospital].title, 'center');

            // console.log(centered, onRight, onLeft, onHidden);

            document.querySelector(onLeft).classList.remove('centered', 'on-right', 'on-left', 'on-hidden')
            document.querySelector(centered).classList.remove('centered', 'on-right', 'on-left', 'on-hidden')
            document.querySelector(onRight).classList.remove('centered', 'on-right', 'on-left', 'on-hidden')
            // document.querySelector(onHidden).classList.remove('centered', 'on-right', 'on-left', 'on-hidden')

            document.querySelector(onLeft).classList.add('centered')
            document.querySelector(centered).classList.add('on-right')
            document.querySelector(onRight).classList.add('on-left')
            // document.querySelector(onHidden).classList.add('on-hidden')

            // const centeredByClass = '.' + this.hospitals[this.defaultHospital].class
            // const onRightByClass = '.' + this.hospitals[right].class
            // const onLeftByClass = '.' + this.hospitals[left].class
            // const onHiddenByClass = '.' + this.hospitals[hidden].class



            // document.querySelector(centered).classList.contains('centered') ? '' : document.querySelector(centered).classList.add('centered')
            // document.querySelector(onRight).classList.contains('on-right') ? '' : document.querySelector(centered).classList.add('on-right')
            // document.querySelector(onLeft).classList.contains('on-left') ? '' : document.querySelector(centered).classList.add('on-left')
            // document.querySelector(onHidden).classList.contains('on-hidden') ? '' : document.querySelector(centered).classList.add('on-hidden')

            // const directions = ['.centered', '.on-right', '.on-left']
            // directions.forEach((directionClass) => {
            //     anime(this[direction][directionClass])
            // })

            // document.querySelector(centered).classList.remove('centered', 'on-right', 'on-left', 'on-hidden')
            // document.querySelector(onRight).classList.remove('centered', 'on-right', 'on-left', 'on-hidden')
            // document.querySelector(onLeft).classList.remove('centered', 'on-right', 'on-left', 'on-hidden')
            // document.querySelector(onHidden).classList.remove('centered', 'on-right', 'on-left', 'on-hidden')

            // document.querySelector(`.${this.hospitals[this.defaultHospital].title}`).classList.add('centered')
            // document.querySelector(`.${this.hospitals[right].title}`).classList.add('on-right')
            // document.querySelector(`.${this.hospitals[left].title}`).classList.add('on-left')
            // document.querySelector(`.${this.hospitals[hidden].title}`).classList.add('on-hidden')



            // document.querySelector('.maternity').classList.add('center')

            // anime({
            //     // targets: centered,
            //     targets: '.maternity',
            //     rotate: [45 + 'deg'],
            //     translateX: [10 + '%'],
            //     // opacity: [1, 0],
            //     // translateX: 250,
            //     easing: 'easeInOutSine',
            //     complete: function(anim) {
            //         // console.log(anim, 'anim');
            //         // console.log(completeLogEl.value, 'completeLogEl.value');
            //         // completeLogEl.value = 'completed : ' + anim.completed;
            //     }
            // })
                // document.querySelector('.maternity').style.backgroundImage = "url(../../assets/animated-hospitals/maternity-hospital/2.png)";
            // setTimeout(() => {
            // })
            // .then(() => {
            //     })

            // document.querySelector(centered).classList.remove('center', 'right', 'left', 'hidden')
            // document.querySelector(onRight).classList.remove('center', 'right', 'left', 'hidden')
            // document.querySelector(onLeft).classList.remove('center', 'right', 'left', 'hidden')
            // document.querySelector(onHidden).classList.remove('center', 'right', 'left', 'hidden')

            // document.querySelector(centered).classList.add('center')
            // document.querySelector(onRight).classList.add('right')
            // document.querySelector(onLeft).classList.add('left')
            // document.querySelector(onHidden).classList.add('hidden')


        }
    },
}
</script>


<style lang="scss">
.campaign-results-animation {
    overflow: hidden;
    min-height: 750px;
    background-image: url('./assets/campaigns/png/2560_1440.png');
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;


    .btn-wrapper {
        display: flex;
        justify-content: space-around;
        position: absolute;
        top: 50px;
        z-index: 10;
        width: 50%;
        left: 50%;
        transform: translateX(-50%);
    }

    .left {

    }

    .center {
        background-image:
            url('./assets/animated-hospitals/maternity-hospital/3.png') !important;
    }

    .right {

    }

    .hidden {

    }

    &__hospitals {
        min-height: 750px;
        width: 100%;
        z-index:5;
        position: relative;

        .maternity {
            height: 750px;
            width: 100%;
            position: absolute;
            background-image:
            url('./assets/animated-hospitals/maternity-hospital/1.png');
            background-position: center;
            background-size: contain;
            background-repeat: no-repeat;
            will-change: transform;
        }

        .city {
            display: none;
            height: 750px;
            width: 100%;
            position: absolute;
            // background-image:
            // url('./assets/animated-hospitals/maternity-hospital/1.png');
            background-position: center;
            background-size: contain;
            background-repeat: no-repeat;
            transform: scale(.8) ;
        }
        .children {
            height: 750px;
            width: 100%;
            position: absolute;
            background-image:
            url('./assets/animated-hospitals/childrens-hospital/2.png');
            background-position: center;
            background-size: contain;
            background-repeat: no-repeat;
            transform: scale(.8) translate(-6%, 9%);
            will-change: transform;
        }
        .onco {
            height: 750px;
            width: 100%;
            position: absolute;
            background-image:
            url('./assets/animated-hospitals/onco-hospital/3.png');
            background-position: center;
            background-size: contain;
            background-repeat: no-repeat;
            transform: scale(.8) translate(5%, 7%);
            will-change: transform;
        }
    }

    .animate {
        animation: .5s move;
        animation-fill-mode: forwards;
        animation-timing-function: ease-out;
    }

    .animateInner {
        animation: .5s moveInner;
        animation-fill-mode: forwards;
        animation-timing-function: ease-out;
    }

    .animateInner-2 {
        animation: .5s moveInner2;
        animation-fill-mode: forwards;
        animation-timing-function: ease-out;
    }

    .animateInner-3 {
        animation: .5s moveInner3;
        animation-fill-mode: forwards;
        animation-timing-function: ease-out;
    }


    @keyframes move {
        from  {
            transform: rotate(45deg);
        }

        to  {
            transform: rotate(30deg) translate(-320px, 300px);
        }
    }
    @keyframes moveInner {
        from  {
            transform: rotate(-45deg);
        }

        to  {
            transform: rotate(-55deg) translate(-50px, 45px);
            height: 650px;
            // opacity: .8;
            // transform: rotate(-28deg) translate(415px, -97px);
            // background-image:
            // url('./assets/animated-hospitals/maternity-hospital/2.png');
        }
    }

    @keyframes moveInner3 {
        from  {
            transform: rotate(-45deg);
        }

        to  {
            // background-image: unset;
            transform: rotate(-55deg) translate(43px, -43px);
            height: 850px;
            // opacity: .8;
        }
    }

    @keyframes moveInner2 {
        0%  {
            transform: rotate(-45deg);
            opacity: 1;
        }

        25% {
            // transform: rotate(-55deg) translate(-50px, 45px);
            opacity: .5;
        }

        50% {
            opacity: 0;
            transform: rotate(-55deg) translate(-50px, 45px);
        }

        55% {
            opacity: 0.1;
            transform: rotate(40deg) translate(1010px, -1025px);
        }

        60% {
            opacity: 0.2;
        }

        65% {
            opacity: 0.3;
        }

        70% {
            opacity: 0.4;
        }

        75% {
            // transform: rotate(34deg) translate(905px, -928px);
            transform: rotate(32deg) translate(936px, -914px);

            opacity: 0.5;
        }

        80% {
            // transform: rotate(15deg) translate(835px, -455px);
            opacity: 0.6;
        }

        85% {
            // transform: rotate(15deg) translate(835px, -455px);
            opacity: 0.7;
        }

        90% {
            // transform: rotate(15deg) translate(835px, -455px);
            opacity: 0.8;
        }
        95% {
            // transform: rotate(15deg) translate(835px, -455px);
            opacity: 0.9;
        }

        100%  {
            // transform: rotate(-55deg) translate(-50px, 45px);
            // transform: rotate(6deg) translate(725px, -345px);

            transform: rotate(22deg) translate(930px, -761px);
            // transform: rotate(34deg) translate(905px, -928px);

            // background-image: unset;
            opacity: 1;
            // transform: rotate(-55deg) translate(43px, -43px);
            // height: 850px;
            // opacity: .8;
        }
    }
}
</style>
