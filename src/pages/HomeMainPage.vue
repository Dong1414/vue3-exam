<template>
    <TitleBar>홈 메인</TitleBar>
     <section class="con">
    <div class="con-min-width text-2xl font-bold m-2">이메일 주소를 입력해주세요</div>
    <span>로그인 아이디로 사용되며, 비밀번호를 잊었을 때 이메일로 임시 비밀번호가 발송됩니다. 공지사항도 발송되므로 실제 사용하는 이메일주소를 입력해 주세요.</span>
    
    <div class="flex-1">
      <span>
        <input class="h-10 email-box" placeholder="이메일">
      </span>
         <span>@</span>
      <span>
       <select class="email-box">
          <option value disabled>선택해주세요</option>
          <option value="naver.com">naver.com</option>
          <option value="hanmail.net">hanmail.net</option>
          <option value="daum.net">daum.net</option>
          <option value="gmail.com">gmail.com</option>
          <option value="nate.com">nate.com</option>
          <option value="hotmail.com">hotmail.com</option>
          <option value="outlook.com">outlook.com</option>
          <option value="icloud.com">icloud.com</option>
          <option value="_manual">직접입력</option>
        </select>
      </span>
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
  .email-box{
    border:solid 2px gray;
  }
</style>

