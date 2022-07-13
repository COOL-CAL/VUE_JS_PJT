<template>
    <div>    
        <h1>My name is Hong.</h1>
        <input type="number" v-model.number="numberModel">
        {{ printNumber }}
        <div>
            <label>Female<input type="radio" v-model.number="gender" value="0"></label>
            <label>Male<input type="radio" v-model="gender" value="1"></label>
        </div>
        <div>{{ gender }}</div>
        <div>{{ printGender }}</div>
        <div>
            <h3>p.96</h3>
            <div> {{ htmlString }}</div>
            <div v-html="htmlString"></div>
        </div>
        <hr>
        <div>
            <h3>p.99</h3>
            <textarea v-model="message"></textarea>
            <!-- input이랑 같게 속성으로 줘야 함. -->
        </div>
        <div>
            <h3>p.100</h3>
            <select v-model="city">
                <option value="02">Seoul</option>
                <option value="21">Busan</option>
                <option value="064">Jeju</option>
            </select>
        </div>
        <div>
            <h3>p.101 - {{ basketball }}, {{ football }}</h3>
            <label><input type="checkbox" v-model="basketball">Basketball</label>
            <label><input type="checkbox" v-model="football" true-value="1" false-value="0">Football</label>
            <br>
        </div>
        <div>
            <input type="text" v-model="textValue1">
            <input type="text" v-model="textValue2">
            <br>
            <button type="button" v-bind:disabled="textValue1 === '' || textValue1 !== textValue2">Send</button>
        </div>
        <div>
            <h3>p.107</h3>
            <div class="container" v-bind:class="{'active': isActive, 'text-red': hasError}">
                Class Binding
            </div>
            <div class="container" :class="[activeClass, errorClass]">
                Class Binding
            </div>
            <div class="container" :class="clsArr">
                Class Binding
            </div>
        </div>
        <hr>
        <div>
            <h3>p.110</h3>
            <div :style="styleObj">Inline style binding</div>
        </div>
    </div>
</template>

<style>
    .container {
        width: 100%;
        height: 200px;
    }
    .active {
        background-color: goldenrod;
        font-weight: bold;
    }
    .text-red { color: red; }
</style>

<script>
export default {
    data() {
        return {
            styleObj: {
                color: 'red',
                fonSize: '16px' //카멜 기법으로 적기
            },
            clsArr: ['active', 'text-red'],
            activeClass: 'active',
            errorClass: 'text-red',
            isActive: true,
            hasError: true,
            numberModel: 3,
            gender: '0',
            htmlString: '<p style="color:red">This is a red string.</p>',
            message: 'This is a Textarea.',
            city: '064',
            basketball: true,
            football: '1',
            textValue1: '',
            textValue2: '',
        }
    },
    computed: { //watch랑 비슷, 계산된 값이 printNumber에 찍히게 함.
        printNumber() {
            return this.numberModel + 3;
        },
        printGender() {
            return this.gender == 0 ? 'Female' : 'Male';
        }
    }
}
</script>
