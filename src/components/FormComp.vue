<template>
    <div>
    <form @submit.prevent="addUser">
        账号：<input type="text" placeholder="请输入账号" v-model="userinfo.userName" /> <br /><br />
        密码: <input type="password" placeholder="请输入密码" v-model="userinfo.password" /><br /><br />
        性别: 
        男<input type="radio" value="male"  v-model="userinfo.sex" /> 
        女<input type="radio" value="famale"  v-model="userinfo.sex"/> <br /><br />
        爱好:
         学习 <input type="checkbox" value="study" v-model="userinfo.hobby" /> 
         游戏 <input type="checkbox" value="game" v-model="userinfo.hobby" /> 
         唱歌 <input type="checkbox" value="sing" v-model="userinfo.hobby" /> <br /><br />
        所在校区: <select v-model="userinfo.school">
            <option value="bj">北京</option>
            <option value="sh">上海</option>
            <option value="gz">广州</option>
        </select> <br /><br />
        其它信息
        <textarea v-model="userinfo.other">

       </textarea> <br /><br />

        <input type="checkbox" v-model="userinfo.agree" /> <span>阅读并接受</span> <a href="">《用户协议》</a> <br /><br />
        <button >提交</button>
    </form>

    <!-- <div>{{time }}</div> -->

</div>
</template>

<script>
// import dayjs from 'dayjs'
export default {
    components: {},
    props: {},
    data() {
        return {
            userinfo:{
                userName:"",
                password:"",
                sex:'male',
                hobby:[],
                school:"",
                other:"",
                agree:false
            },
            time:'1669561081517'

        };
    },
    watch: {},
    computed: {},
    methods: {
        addUser(){
            console.log('addUser',this.userinfo);
        }
    },
    // filters:{
    //     fmttime(value){
    //         // console.log('filterFmtTime',value);
    //         // return  dayjs(value).format('YYYY-MM-DD');
    //     }
    // },
    created() { },
    mounted() { },
   
};
</script>
<style lang="scss" scoped>

</style>