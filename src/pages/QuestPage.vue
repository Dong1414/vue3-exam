<template>
  <TitleBar>홈 메인</TitleBar>

  <div class="bg-white p-3 shadow-sm rounded-sm w-2/3 m-auto">
  
                    <div class="flex items-center space-x-2 font-semibold text-gray-900 leading-8">
                        <span clas="text-green-500">
                            <svg class="h-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"></path>
                            </svg>
                        </span>
                    
                        <span class="tracking-wide">의뢰 요청서</span>
                    </div>
                    <div class="text-gray-700">                        
                            <div class="flex">
                                <div class="px-4 py-2 font-semibold">의뢰인 이름</div>
                                <div class="px-4 py-2">{{ state.article.extra__writer }}</div>
                            </div>
                            <div class="flex">
                                <div class="px-4 py-2 font-semibold">연락처</div>
                                <div class="px-4 py-2">{{state.article.extra__cellphoneNo}}</div>
                            </div>
                            <div class="flex">
                                <div class="px-4 py-2 font-semibold">요청시간</div>
                                <div class="px-4 py-2">{{state.article.regDate}}</div>
                            </div>
                            <div class="flex">
                                <div class="px-4 py-2 font-semibold">요청 장소</div>
                                <div class="px-4 py-2">대전 건양대</div>
                            </div>
                            <div class="flex">
                                <div class="px-4 py-2 font-semibold">요청 기간</div>
                                <div class="px-4 py-2">2021-02-03 ~ 2021-02-05</div>                                
                            </div>
                            <div class="flex">
                                <div class="px-4 py-2 font-semibold">기본 요청 서비스</div>
                                <div class="px-4 py-2"> <ul><li>땡땡땡</li><li>땡땡땡땡땡땡</li><li>땡땡땡땡땡땡땡땡땡</li></ul></div>
                            </div>
                            <div class="flex">
                                <div class="px-4 py-2 font-semibold">더 필요한게 생기면 추가 예정</div>                                
                            </div>                            
                        </div>
                    </div>
                    <button class="block text-blue-800 text-sm font-semibold rounded-lg hover:bg-gray-300 focus:outline-none focus:shadow-outline hover:shadow-xs p-3 my-4 w-2/3 m-auto">수락</button>
                
</template>

<script lang="ts">
import { defineComponent, ref, reactive, getCurrentInstance, onMounted, watch } from 'vue'
import { useRoute } from 'vue-router'
import { IArticle } from '../types'
import { MainApi } from '../apis'

export default defineComponent({
  name: 'QuestPage',
   props: {
    globalShare: {
      type: Object,
      required: true
    },
    id: {
      type: Number,
      required: true,
      default:1
    }
  },
  setup(props) {
    const mainApi:MainApi = getCurrentInstance()?.appContext.config.globalProperties.$mainApi;
    const state = reactive({
      article: {} as IArticle
    });
    function loadArticle(id:number) {
      mainApi.article_detail(id)
      .then(axiosResponse => {
        state.article = axiosResponse.data.body.article;
      });
    }
    onMounted(() => {
      loadArticle(props.id);
    });
    watch(() => props.id, (newValue, oldValue) => {
      loadArticle(props.id);
    })
    return {
      state,
    }
  }
})
</script>

<style scoped>
</style>