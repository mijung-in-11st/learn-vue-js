<template>
  <!-- 
    
      컴포넌트 명명법
    <hello-world></hello-world>
    <HelloWorld></HelloWorld>
    <HelloWorld/> : 가장 진보된 명명법
    
  -->
  <div>
    <!-- root는 하나만 있어야함 -->
    {{ str }}
    <!-- v-bind:프롭스 속성이름(하위 컴포넌트)="상위 컴포넌트 데이터이름"-->
    <app-header 
      v-bind:propsdata="str"
      v-on:renew="renewStr"></app-header>
  </div>  
</template>

<script>
// import 변수명 from '파일 위치';
// 파일 내용을 변수에 담음
import AppHeader from './components/AppHeader.vue';

// var AppHeader = {
//   template: '<header><h1>Header</h1></header>'
// }

export default {
  //JavaScript - component option
  // function으로 만들고 객체 반환
  data: function() {
    return {
      str: 'Header'
    }
  },
  components: {
    'app-header': AppHeader
  },
  methods: {
    renewStr: function() {
      this.str = 'hi';
    }
  }
}
</script>

<style>

</style>