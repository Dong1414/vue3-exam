<template>
    <TitleBar>홈 메인</TitleBar>
     <section class="con">
    <div class="con-min-width text-2xl font-bold m-2">kakao</div>
        
    
      <div>
        <input class="h-10 m-4 loginId" placeholder="카카오메일 아이디, 이메일, 전화번호">
      </div>
      <div>
        <input class="h-10 m-4 loginPw" type="password" placeholder="비밀번호">
      </div>
    </section>         
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HomeMainPage',
  components: {

  }
})
</script>

<style scoped>
  .loginId{
    border-bottom:solid 2px gray;
    width:350px;
  }
  input[type="password"]{
    border:transparent;
  }
  .loginPw{
    border-bottom:solid 2px gray !important;
    padding-left: 0;
    width:350px;
  }
  input{
    border: none !important;
    outline: none !important;
  }

</style>

