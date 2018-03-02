<template>
    <div class="wrapper">
        <text class="tlt">{{toptitle}}</text>
        <scroller class="scroll" scroll-direction="horizontal" flex-direction="row" show-scrollbar=false>
            <div class="box" v-for="i in topics">
                <image class="box-img" resize="cover" :src="i.img"></image>
            </div>
        </scroller>
    </div>
</template>
<style scoped>
    .iconfont {
        font-family:iconfont;
    }
    .wrapper{
        background-color: #fff;
    }

    .tlt{
        text-align: left;
        color:#333;
        width: 750px;
        padding: 17px;
        font-size: 30px;
        top: 15px;
    }
    .scroll{
        height: 350px;
    }
    .box{
        width: 450px;
        height: 300px;
        margin-top: 30px;
        margin-left: 17px;
        margin-bottom: 17px;
    }
    .box-img{
        position: absolute;
        top:0;
        left: 0;
        width: 450px;
        height: 275px;
    }

</style>
<script>
    export default {
        props:["topics","toptitle"],
        data () {
            return {
            }
        },
        methods: {
        }
    }
</script>