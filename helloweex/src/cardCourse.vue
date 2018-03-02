<template>
    <div class="wrapper">
        <text class="tlt">精选好课</text>
        <div class="cards">
            <div class="c-courses" v-for="n in Courses"  @click="pushToWeb(n.weburl)">
                <image class="c-img" resize="cover" :src="n.imageurl"></image>
                <text class="c-tit">{{n.coursetitle}}</text>
                <star class="c-star" :score="n.score"></star>
                <text class="c-learn">{{n.leran}}人学过</text>
                <text class="c-price">¥{{n.price}}</text>
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
        height: 500px;
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
    .c-star{
        margin-top: 10px;
        width: 350px;
        height: 26px;
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
    .c-price{
        font-size: 28px;
        width: 350px;
        margin-top: 10px;
        color:#b4282d;
        overflow: hidden;
        lines:1;
        white-space: nowrap;
        text-overflow: ellipsis;
    }
</style>
<script>
    var navigator = weex.requireModule('navigator')
    var openModule = weex.requireModule('open')
    export default {
        data () {
            return {
                imageurl : 'http://edu-image.nosdn.127.net/EF84648F025F25CBD50C78E938282A55.jpg',
                coursetitle : '基金定投（高级篇)',
                score:'4.8113',
                leran:'256',
                Courses: [
                    { imageurl:'http://edu-image.nosdn.127.net/EF84648F025F25CBD50C78E938282A55.jpg?imageView&thumbnail=960y600&quality=100', coursetitle:'基金定投（高级篇)', score:'4.8113', leran:'256', price:'80', weburl:'http://study.163.com/course/introduction/1003844366.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxNX1RBR3wwLjEzNg..&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/77FB817D044CE41F2EA284A78D9ACFEA.jpg?imageView&thumbnail=960y600&quality=100', coursetitle:'12堂声音美化课，全面提升个人魅力', score:'4.604', leran:'527', price:'99', weburl:'http://study.163.com/course/introduction/1004488005.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxNX1RBR3wwLjExMQ..&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/13ED8C2A9B42D0D1B573919907422F59.jpg?imageView&thumbnail=448x248&quality=100', coursetitle:'楼市进入分水岭，这样买房能再升值', score:'4.604', leran:'1231', price:'99', weburl:'http://study.163.com/course/introduction/1004543001.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxQT1NGSUx8MC4w&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/4A28412EEBDB76426BD53AF9C2F1EBCF.png?imageView&thumbnail=448x248&quality=100', coursetitle:'跟500强工程师学职场商务英语', score:'4.604', leran:'127', price:'99', weburl:'http://study.163.com/course/introduction/1004495007.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxQT1NGSUx8MC4w&recommendRequestId='},
                    { imageurl:'http://img0.ph.126.net/p6Wm1AVf32poMdX_rVs5EQ==/6630718121003308134.jpg', coursetitle:'5阶段教你吃透投资理财', score:'4.604', leran:'527', price:'99', weburl:'http://study.163.com/course/introduction/701017.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxQT1NGSUx8MC4xMjM.&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/7B0763A4D8B0BBD590D25259250719DE.jpg?imageView&thumbnail=960y600&quality=100', coursetitle:'和秋叶一起学Word—超1.5万人付费', score:'4.604', leran:'4527', price:'99', weburl:'http://study.163.com/course/introduction/747046.htm?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxQT1NGSUx8MC4xMjM.&recommendRequestId='}
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