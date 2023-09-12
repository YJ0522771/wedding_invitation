<template>
    <div class="contact">
        <Headline
        headline="마음을 전하는 곳"/>
        <div class="accordion">
            <div class="accordion-item">
                <h2 class="accordion-header">
                    <button :class="{'accordion-button': true, 'collapsed': !visible1}" type="button" data-bs-toggle="collapse" @click="click1">
                        <img src="@/assets/icons/L.png" class="img"><div class="according-title">신랑 측에 마음 전하기</div>
                    </button>
                </h2>
                <div :class="{'accordion-collapse': true, 'collapse': true, 'show': visible1}" >
                    <div class="accordion-body accounts"
                    v-for="e in account1"
                    :key="e.name">
                        <p class="name">{{ e.name }}</p>
                        <div class="account"><span>{{ e.bank }}</span> <span>{{ e.account }}</span><button class="btn" @click="copy(e.name)"><i class="fas fa-copy"></i></button></div>
                    </div>
                </div>
            </div>
            <div class="accordion-item">
                <h2 class="accordion-header">
                    <button :class="{'accordion-button': true, 'collapsed': !visible2}" type="button" @click="click2">
                        <img src="@/assets/icons/J2.png" class="img"><div class="according-title">신부 측에 마음 전하기</div>
                    </button>
                </h2>
                <div :class="{'accordion-collapse': true, 'collapse': true, 'show': visible2}">
                    <div class="accordion-body accounts"
                    v-for="e in account2"
                    :key="e.name">
                        <p class="name">{{ e.name }}</p>
                        <div class="account"><span>{{ e.bank }}</span> <span>{{ e.account }}</span><button class="btn" @click="copy(e.name)"><i class="fas fa-copy"></i></button></div>
                        
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Headline from './Headline.vue'

export default {
    name: 'Contact',
    props: {
    },
    components: {
        Headline,
    },
    data: function() {
        return {
            account1: [
                {
                    name: '이준우',
                    bank: '기업은행',
                    account: '278-063342-01-013'
                },
                {
                    name: '이기영',
                    bank: '농협',
                    account: '741011-56-203312'
                },
                {
                    name: '이화연',
                    bank: '농협',
                    account: '741011-52-188776'
                }
            ],
            account2: [
                {
                    name: '조유진',
                    bank: '기업은행',
                    account: '278-069160-01-019'
                },
                {
                    name: '조재천',
                    bank: '농협',
                    account: '356-1544-5005-63'
                },
                {
                    name: '이길남',
                    bank: '산업은행',
                    account: '020-4702-2155-850'
                }
            ],
            visible1: false,
            visible2: false
        }
    },
    methods: {
        click1: function () {
            if (this.visible1 == true) {
                this.visible1 = false;
            }
            else {
                this.visible1 = true;
                if (this.visible2 == true) {
                    this.visible2  = false;
                }
            }
            console.log(this.visible1);
        },
        click2: function () {
            if (this.visible2 == true) {
                this.visible2 = false;
            }
            else {
                this.visible2 = true;
                if (this.visible1 == true) {
                    this.visible1  = false;
                }
            }
            console.log(this.visible1);
        },
        copy: function (name) {
            for (var i = 0; i < this.account1.length; i++)
            {
                if (this.account1[i].name === name) {
                    this.$copyText(this.account1[i].bank + " " + this.account1[i].account).then(()=> {
                        alert("복사 완료.");
                    })
                    return;
                }
            }
            for (i = 0; i < this.account2.length; i++)
            {
                if (this.account2[i].name === name) {
                    this.$copyText(this.account2[i].bank + " " + this.account2[i].account).then(()=> {
                        alert("복사 완료.");
                    })
                    return;
                }
            }
        }
    },
}
</script>

<style scoped>
.contact {
    margin: 50vw 0;
}
.accordion {
    width: 90%;
    margin: 5vw;
    margin-top: 10vw;
    padding-bottom: 10vw;
    z-index: 1;
    position: relative;
}
.accounts {
    text-align: start;
    font-family: 'Noto Serif KR', serif;
}
.name {
    font-weight: bold;
}
.account {
    margin-left: 5vw;
}
.btn {
    margin: 1vw 0;
    padding: 0;
    width: 6vw;
    height: 6vw;
}
.btn-text {
    font-weight: bold;
}
.copy  {
    width: 3vw;
    height: 3vw;
    margin: 0;
}
.img {
    width: 7vw;
    height: 7vw;
    margin: auto 3vw;
    display: inline-flex;
}
.according-title {
    font-size: 1.2rem;
    font-family: 'Nanum Brush Script', cursive;
}
</style>