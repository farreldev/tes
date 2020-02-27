<template>
    <div class="calculator">
        <div class="content-calculator">
            <h1>Calculator Biasa</h1>
            <div class="wrapper-form">
                <div class="group-field">
                    <input type="text" v-model="inp1" placeholder="Input 1...">
                    <input type="checkbox" :value="parseInt(inp1)" name="" v-model="tampung" id="">
                </div>
                <div class="group-field">
                    <input type="text" v-model="inp2" placeholder="Input 2...">
                    <input type="checkbox" :value="parseInt(inp2)" name="" v-model="tampung" id="">
                </div>
                <div class="group-field">
                    <input type="text" v-model="inp3" placeholder="Input 3...">
                    <input type="checkbox" :value="parseInt(inp3)" name="" v-model="tampung" id="">
                </div>
            </div>
            <div class="group-btn">
                <ul>
                    <li>
                        <button @click="validate('x')">x</button>
                    </li>
                    <li>
                        <button @click="validate('+')">+</button>
                    </li>
                    <li>
                        <button @click="validate('-')">-</button>
                    </li>
                    <li>
                        <button @click="validate('/')">/</button>
                    </li>
                </ul>
            </div>
            <div class="result">
                <strong>{{ hasil }}</strong>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Calculator',
    data(){
        return {
            inp1:null,
            inp2:null,
            inp3:null,
            tampung: [],
            hasil: 0
        }
    },
    methods: {
        validate(c) {
            if(this.tampung.length != 1) {
                switch(c) {
                    case 'x':
                        this.hasil = this.tampung.reduce((acc, val) => acc * val);
                        break;
                    case '+':
                        this.hasil = this.tampung.reduce((acc, val) => acc + val);
                        break;
                    case '-':
                        this.hasil = this.tampung.reduce((acc, val) => acc - val);
                        break;
                    case '/':
                        this.hasil = this.tampung.reduce((acc, val) => acc / val);
                        break;
    
                }
            } else {
                alert('Oopss, cuma satu? Minimal harus dua bilangan')
            }
        }
    }
}
</script>

<style lang="scss">
.calculator {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(75, 188, 216);
    .content-calculator {
        padding: 20px 10px;
        border-radius: 5px;
        min-width: 300px;
        min-height: 400px;
        background-color: white;
        h1 {
            text-align: center;
        }
        .wrapper-form {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            .group-field {
                display: flex;
                align-items: center;
                border: 1px solid #ddd;
                margin-bottom: 15px;
                input[type="text"] {
                    padding: 5px 0;
                    text-indent: 10px;
                    border: none;
                }
            }
        }
        .group-btn {
            padding-bottom: 16px;
            border-bottom: 1px solid #ddd;
            display: flex;
            justify-content: center;
            ul {
                padding: 0;
                margin: 0;
                list-style: none;
                display: block;
                li {
                    margin: 0 3px;
                    display: inline-block;
                    button {
                        padding: 7px 10px;
                    }
                }
            }
        }
        .result {
            font-size: 55px;
            text-align: center;
        }
    }
}
</style>