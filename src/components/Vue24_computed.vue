<template>
  <h1>Computed</h1>
  <h3>ref, reactive, watcher 모두 실시간으로 데이터 변경을 반영하지만 특별히 계산된 속성을 반영하고자 할때 사용</h3>
  <h2>Small item</h2>
  <p v-for="item in smallItemsO" :key="item">{{item.text}}</p>
  <p v-for="item in smallItemsC" :key="item">{{item.text}}</p>
  <h2>Big item</h2>
  <p v-for="item in bigItemsO" :key="item">{{item.text}}</p>
  <p v-for="item in bigItemsC" :key="item">{{item.text}}</p>
</template>

<script>
import { computed, reactive } from '@vue/runtime-core'

export default {
    data(){
        return{
            arr:[
                {id:1, text:'1번 옵션 아이템'},
                {id:2, text:'2번 옵션 아이템'},
                {id:3, text:'3번 옵션 아이템'},
                {id:4, text:'4번 옵션 아이템'},
                {id:5, text:'5번 옵션 아이템'},
            ]
        }
    },
    computed:{smallItemsO() {
        return this.arr.filter(i =>i.id<3)
    },
    bigItemsO(){
        return this.arr.filter(i => i.id>=3)
    }
    },
    setup(){
        const arr= reactive([
                {id:1, text:'1번 옵션 아이템'},
                {id:2, text:'2번 옵션 아이템'},
                {id:3, text:'3번 옵션 아이템'},
                {id:4, text:'4번 옵션 아이템'},
                {id:5, text:'5번 옵션 아이템'},
            ])
        const smallItemsC = computed(
            ()=>arr.filter(i=>i.id<3)
        )
        const bigItemsC = computed(
            ()=>arr.filter((i)=>i.id>=3)
        )
        return{smallItemsC,bigItemsC}
    }
}
</script>

<style>

</style>