<template>
    <div>
        <div>人员列表 
             <button @click="this.sortType = 1"> 升序</button>    &nbsp;
             <button  @click="this.sortType = 2"> 降序</button>   &nbsp;
             <button  @click="this.sortType = 0">原顺序</button></div> <br />
        <input type="text" placeholder="请输入人员姓名" v-model="keyWord" />

        <ul>
            <li v-for="p in filterPersons" :key="p.id">
                <span>姓名: {{ p.name }} -- 年龄:{{ p.age }}</span>
            </li>
        </ul>


    </div>
</template>

<script>
export default {
    components: {},
    props: {},
    data() {
        return {
            keyWord: "",
            sortType:0,
            persons: [
                { id: 1, "name": '周冬雨', age: 14 },
                { id: 2, "name": '马冬梅', age: 16 },
                { id: 3, "name": '周杰伦', age: 15 },
                { id: 4, "name": '温兆伦', age: 17 },
            ],
            filPersons:[]
        };
    },
    watch: {
        // keyWord: {
        //     immediate: true,
        //     handler(val,old) {
        //         console.log('val:'+val,'old:'+old)
        //         this.filPersons = this.persons.filter((p)=>{
        //             return p.name.indexOf(val) != -1;
        //         })
        //     }
        // }

    },
    computed: {
        filterPersons() {
            const arr =  this.persons.filter((p) => {
                return p.name.indexOf(this.keyWord) != -1;
            });
            console.log('sortType: '+this.sortType);
            if(this.sortType){
                arr.sort((p1,p2)=>{
                    return this.sortType === 1 ? p2.age - p1.age : p1.age-p2.age
                })
            }

            return arr;

        }
    },
    methods: {},
    created() { },
    mounted() { }
};
</script>
<style lang="scss" scoped>

</style>