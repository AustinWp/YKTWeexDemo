<template>
    <div class="wrapper">
        <text class="tlt">免费好课</text>
        <div class="cards">
            <div class="c-courses" v-for="n in Courses"  @click="pushToWeb(n.weburl)">
                <image class="c-img" resize="cover" :src="n.imageurl"></image>
                <text class="c-tit">{{n.coursetitle}}</text>
                <text class="c-learn">{{n.leran}}人学过</text>
            </div>
        </div>
    </div>
</template>
<style scoped>
    .iconfont {
        font-family:iconfont;
    }
    .wrapper{
        background-color: #fff;
        padding-bottom: 10px;
        padding-top: 15px;
        width: 750px;
    }
    .tlt{
        text-align: left;
        color:#333;
        width: 750px;
        padding: 17px;
        font-size: 30px;
    }
    .cards{
        padding: 17px;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-between;
    }
    .c-courses{
        width: 350px;
        height: 420px;
        margin-bottom: 30px;
    }
    .c-img{
        width: 350px;
        height: 300px;
        background-color: #f4f4f4;
    }

    .c-tit{
        font-size: 28px;
        color:#333;
        width: 350px;
        margin-top: 10px;
        overflow: hidden;
        lines:2;
        text-overflow: ellipsis;
    }
    .c-learn{
        font-size: 24px;
        width: 350px;
        margin-top: 10px;
        color:#a4a9b2;
        overflow: hidden;
        lines:1;
        white-space: nowrap;
        text-overflow: ellipsis;
    }
</style>
<script>
    var openModule = weex.requireModule('open')
    export default {
        data () {
            return {
                Courses: [
                    { imageurl:'http://edu-image.nosdn.127.net/AEAA695BE9DF3EA3A2D5263C38DC8B92.jpg?imageView&thumbnail=960y600&quality=100', coursetitle:'After Effects CC基础教程', score:'4.8113', leran:'50281', price:'80', weburl:'http://study.163.com/course/introduction/730009.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxQT1NGSUx8MC4yMDg.&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/8db58bc8-660f-4892-bc7d-9b77a68097d3.jpg?imageView&quality=100', coursetitle:'给职场新人的Excel课', score:'4.604', leran:'182730', price:'99', weburl:'http://study.163.com/course/introduction/1002886001.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxQT1NGSUx8MC43Nzg.&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/8640D3550398881414C4ADB02A39E72E.jpg?imageView&thumbnail=960y600&quality=100', coursetitle:'MIDI音乐制作乐理基础入门教程', score:'4.604', leran:'1589', price:'99', weburl:'http://study.163.com/course/introduction/1003727009.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxQT1NGSUx8MC4w&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/18C953755FB357B9283716FF6200BFF0.jpg?imageView&thumbnail=960y600&quality=100', coursetitle:'歌唱初学者的十堂必修课', score:'4.604', leran:'114716', price:'99', weburl:'http://study.163.com/course/introduction/1712008.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxQT1NGSUx8MC4w&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/77FB817D044CE41F2EA284A78D9ACFEA.jpg?imageView&thumbnail=960y600&quality=100', coursetitle:'手机美食摄影入门教程', score:'4.604', leran:'3606', price:'99', weburl:'http://study.163.com/course/introduction/1004113084.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxQT1NGSUx8MC4w&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/69950DCCF7F3922E62EB42FEEED6D44F.jpg?imageView&thumbnail=960y600&quality=100', coursetitle:'FitTime 马甲线养成计划', score:'4.604', leran:'42429', price:'99', weburl:'http://study.163.com/course/introduction/1003055003.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxQT1NGSUx8MC4xNjc.&recommendRequestId='}
                ]
            }    
        },
        methods: {
            pushToWeb (_url) {
                if(!_url) return;
                openModule.openURL(_url,function(ret) {   
                    nativeLog(ret);
                });
            }


        }
    }
</script>