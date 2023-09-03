<template>
    <div class="contact">
        <h3>매미 전하는 곳</h3>
        <div class="accordion">
            <div class="accordion-item">
                <h2 class="accordion-header">
                    <button :class="{'accordion-button': true, 'collapsed': !visible1}" type="button" data-bs-toggle="collapse" @click="click1">
                        신랑 측 계좌번호
                    </button>
                </h2>
                <div :class="{'accordion-collapse': true, 'collapse': true, 'show': visible1}" >
                    <div class="accordion-body accounts"
                    v-for="e in account1"
                    :key="e.name">
                        <p class="name">{{ e.name }}</p>
                        <div class="account"><span>{{ e.bank }}</span> <span>{{ e.account }}</span><button @click="copy(e.name)"></button></div>
                    </div>
                </div>
            </div>
            <div class="accordion-item">
                <h2 class="accordion-header">
                    <button :class="{'accordion-button': true, 'collapsed': !visible2}" type="button" @click="click2">
                        신부 측 계좌번호
                    </button>
                </h2>
                <div :class="{'accordion-collapse': true, 'collapse': true, 'show': visible2}">
                    <div class="accordion-body accounts"
                    v-for="e in account2"
                    :key="e.name">
                        <p class="name">{{ e.name }}</p>
                        <div class="account"><span>{{ e.bank }}</span> <span>{{ e.account }}</span><button @click="copy(e.name)"></button></div>
                        
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Contact',
    props: {
        
    },
    components: {
    },
    data: function() {
        return {
            account1: [
                {
                    name: '이준우',
                    bank: '국민은행',
                    account: '1234567890'
                },
                {
                    name: '이준우',
                    bank: '기업은행',
                    account: '1234567890'
                },
                {
                    name: '이준우',
                    bank: '하나은행',
                    account: '1234567890'
                }
            ],
            account2: [
                {
                    name: '조유진',
                    bank: '국민은행',
                    account: '1234567890'
                },
                {
                    name: '조유진',
                    bank: '기업은행',
                    account: '1234567890'
                },
                {
                    name: '조유진',
                    bank: '하나은행',
                    account: '1234567890'
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
                    this.$copyText(this.account1[i].bank + " " + this.account1[i].account).then(()=> {})
                    return;
                }
            }
            for (i = 0; i < this.account2.length; i++)
            {
                if (this.account2[i].name === name) {
                    this.$copyText(this.account2[i].bank + " " + this.account2[i].account).then(()=> {})
                    return;
                }
            }
        }
    },
}
</script>

<style scoped>
.accordion {
    width: 70vw;
    margin: 10vw auto;
}
.accounts {
    text-align: start;
}
.name {
    font-weight: bold;
}
.account {
    margin-left: 5vw;
}
.btn {
    margin: 1vw 0;
}
.btn-text {
    font-weight: bold;
}
</style>