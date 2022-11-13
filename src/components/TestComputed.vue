<template>
    <div>

        <div>姓：<input type="text" v-model="firstName" /></div>
        <div>名：<input type="text" v-model="lastName" /></div>
        <div>全名：{{ firstName + "-" + lastName }}</div>
        <div>全名：methods: {{ getFullName() }}</div>
        <div>全名： computed: {{ comFullName }}</div>
        <div>全名 watch：{{ this.fullName }}</div>

        <div class="basic" :class="classArr" @click="changeMood">我今天的心情</div>

        <div v-show="false"> 显示和隐藏1</div>
        <div v-if="false"> 显示和隐藏2</div>

        <div v-if="a === 1"> angluar</div>
        <div v-else-if="a === 2"> vue</div>
        <div v-else> react</div>


        遍历数组
        <ul>
            <li v-for="item in persons" :key = "item.id">
                <span >姓名： {{item.name}} --- 年龄: {{item.age}}</span>
            </li>
        </ul>

        遍历对象
        <ul>
            <li v-for=" (val,key) in car" :key = "key">
                <span > {{val}}</span>
            </li>
        </ul>

    </div>

</template>

<script>

export default {
    name: 'TestComputed',
    data() {
        return {
            a: 4,
            firstName: '',
            lastName: '',
            fullName: "",
            classArr: '',
            persons:[
                {id:1,name:'bella',age:32},
                {id:2,name:'miao',age:22},
                {id:3,name:'cong',age:31},
            ],
            car:{
                band:'奥迪',
                color:'red',
                type:'SUV'
            }
        }
    },
    methods: {
        getFullName() {
            return this.firstName + "-" + this.lastName;
        },
        changeMood() {
            const arr = ['happy', 'sad', 'background'];
            const index = Math.floor(Math.random() * 3);
            this.classArr = arr[index];
        }
    },
    computed: {
        // fullName:{
        //    get(){
        //     return this.firstName + "-"+this.lastName ;
        //    }
        // }
        comFullName() {
            return this.firstName + "-" + this.lastName;
        }
    },
    watch: {
        firstName(val) {
            setTimeout(() => {
                this.fullName = val + "-" + this.lastName
            }, 1000);
        },
        lastName(val) {
            setTimeout(() => {
                this.fullName = this.firstName + "-" + val
            }, 1000);
        }

    }


}
</script>


<style scoped>
.basic {
    width: 100px;
    height: 60px;
    border: 1px solid #f8f8f8;
}

.happy {
    background: green;
}

.sad {
    background: gray;
}

.nombal {
    background: f8f8f8;
}
</style>