<template>
  <div class="wrapper" @click="update">
    <scroller class="main-list" offset-accuracy="300px">
      <ykt-banner :imageList="Banners" ></ykt-banner>
      <ykt-course></ykt-course>
      <div class="grayline"></div>
      <ykt-scroll :topics="Topics" :toptitle="topicTitle"></ykt-scroll>
      <div class="grayline"></div>
      <ykt-feecourse></ykt-feecourse>
      <div class="grayline"></div>
      <ykt-scroll :topics="sCourses" :toptitle="sCourseTitle"></ykt-scroll>
      <div class="grayline"></div>
      <ykt-book></ykt-book>
    </scroller>
  </div>
</template>

<style>
  .wrapper { background-color: #f4f4f4;}
  .grayline { height: 20px; background-color: #f2f4f7}
  .main-list{
    }
</style>

<script>
  import Banner from './banner.vue';
  import Course from './cardCourse.vue';
  import Scroll from './cardScroll.vue';
  import feeCourse from './cardFeeCourse.vue';
  import Book from './cardBook.vue';
  export default {
    components: {
            'ykt-banner': Banner,
            'ykt-course': Course, 
            'ykt-scroll': Scroll,
            'ykt-feecourse': feeCourse,
            'ykt-book': Book,      
        },
    data: {
      logoUrl: 'http://img1.vued.vanthink.cn/vued08aa73a9ab65dcbd360ec54659ada97c.png',
      target: 'World'
    },
    data() {
      return {
        Banners: [
                  { title: '', src: 'http://edu-image.nosdn.127.net/3CA103E8189E6C987B0DC527E2AF70B5.jpg?imageView&thumbnail=1242y570&quality=100'},
                  { title: '', src: 'http://edu-image.nosdn.127.net/f595786d-a5f5-4e05-a98b-c990d98e94ec.jpg?imageView&quality=100'},
                  { title: '', src: 'http://edu-image.nosdn.127.net/B5AEC7184E9BB2E218CF1F89F3B7D977.jpg?imageView&thumbnail=1242y570&quality=100'},
                  { title: '', src: 'http://edu-image.nosdn.127.net/68164DC07AA3F105ACD7FF6134E8DC00.png?imageView&thumbnail=1242y570&quality=100'},
                  { title: '', src: 'http://edu-image.nosdn.127.net/71b7dd84-c385-464f-9bfa-66fca71aa454.jpg?imageView&quality=100'},
                  { title: '', src: 'http://edu-image.nosdn.127.net/D296A7AC189FE541B256C235C9FE57FA.png?imageView&thumbnail=1242y570&quality=100'},
                  { title: '', src: 'http://edu-image.nosdn.127.net/f6b78221-f54e-4d62-8f37-d6913e0b9177.jpg?imageView&quality=100'}
              ],
        Topics: [
            { img: 'http://edu-image.nosdn.127.net/df7235ca-f4cc-4876-86cf-152984267e01.jpg?imageView&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/72dd6a8e-b413-41e1-8f41-4d9397a4264f.jpg?imageView&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/2740f923-4e87-44ce-b7f8-972f988bc02d.jpg?imageView&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/D8195CBF53D3FCAF2BCA99A7AF68C3D3.png?imageView&thumbnail=774y483&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/5ead7a7e-f1a1-4dfd-982c-28818bd7c256.jpg?imageView&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/68638149-7008-4e1f-9d90-6670e2e616f3.jpg?imageView&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/68638149-7008-4e1f-9d90-6670e2e616f3.jpg?imageView&quality=100'}
        ],

        topicTitle : "专题",

        sCourses: [
            { img: 'http://edu-image.nosdn.127.net/8E4AD9CFA182843AA62A2420D7620240.png?imageView&thumbnail=774y483&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/C2A271CE9F92777EEAFB04F90F895FA6.jpg?imageView&thumbnail=774y483&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/D5BA4115D68817398AFE2F79727E95A2.jpg?imageView&thumbnail=774y483&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/305a4b40-4158-4311-91db-91d64bf6907d.jpg?imageView&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/009f52ad-ff3c-4f7f-9e57-17503ff60391.jpg?imageView&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/ffd40108-0d8c-4a79-a813-0e8aa3a513b2.jpg?imageView&quality=100'},
            { img: 'http://edu-image.nosdn.127.net/68638149-7008-4e1f-9d90-6670e2e616f3.jpg?imageView&quality=100'}
        ],

        sCourseTitle : "系列课程",

      }

    },
    methods: {
      update: function (e) {
        this.target = '这个是weex的target！'
        console.log('target:', this.target)
      }
    }
  }
</script>