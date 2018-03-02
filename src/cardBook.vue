<template>
    <div class="wrapper">
        <text class="tlt">精选书籍</text>
        <div class="cards">
            <div class="c-books" v-for="n in Books"  @click="pushToWeb(n.weburl)">
                <image class="c-img" resize="cover" :src="n.imageurl"></image>
                <text class="c-tit">{{n.coursetitle}}</text>
                <text class="c-learn">{{n.leran}}人学过</text>
            </div>
        </div>
        <text class="bottomtext">- 到底了 -</text>
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
    .bottomtext{
        text-align: center;
        color: #333;
        width: 750px;
        font-size: 24px;
    }
    .cards{
        padding: 17px;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-between;
    }
    .c-books{
        width: 225px;
        height: 450px;
        margin-bottom: 30px;
    }
    .c-img{
        width: 225px;
        height: 300px;
        background-color: #f4f4f4;
    }

    .c-tit{
        font-size: 28px;
        color:#333;
        width: 225px;
        margin-top: 10px;
        overflow: hidden;
        lines:2;
        text-overflow: ellipsis;
    }
    .c-learn{
        font-size: 24px;
        width: 225px;
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
                Books: [
                    { imageurl:'http://edu-image.nosdn.127.net/e828e324-d8a8-419b-b7b3-e0e76c86f95d', coursetitle:'心理学与读心术', score:'4.8113', leran:'27', price:'80', weburl:'http://study.163.com/book/1004042057?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxNX1RBR3wwLjA4OQ..&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/6bf658ca-261e-4f3b-8aad-8578e37bb901', coursetitle:'7S倍速学习法', score:'4.604', leran:'289', price:'99', weburl:'http://study.163.com/book/1004049033?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxNX1RBR3wwLjEyNw..&recommendRequestId='},
                    { imageurl:'http://edu-image.nosdn.127.net/47420520-3788-4c94-9cba-83e52298296f', coursetitle:'巴菲特最有价值的8条投资商律', score:'4.604', leran:'1589', price:'99', weburl:'http://study.163.com/book/1003837085?recommendScene=c3RfbW9iX3Bvc2l0aW9u&recommendAlgInfo=YmFzZXxNX1RBR3wwLjEyNQ..&recommendRequestId='}
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