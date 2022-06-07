<template>
  <h1>watchEffect</h1>
  <h3>코드로 지정한 변수값을 감시, 콜백함수로 부가적인 작업 추가 가능</h3>
  <p>{{countO}}</p>
  <button @click="countO++">Options </button>
  <p>{{countC}}</p>
  <button @click="countC++">Composition </button>
  <p>{{countC1}}</p>
  <button @click="countC1++">Composition 2</button>
  <p>상태 : {{state}}</p>
  <button @click="onStop()">stop watchEffect </button>
</template>

<script>
import { ref } from '@vue/reactivity';
import { watch, watchEffect } from '@vue/runtime-core';
export default {
    data(){
        return{countO:0}
    },
    watch:{
        countO: function(cur, prev){
            console.log(`options API watch: ${prev} ==>${cur}}`);
        }
    },
    setup(){
        const countC = ref(0)
        const countC1 = ref(0)
        const state= ref('실행중')
        watch(
            [countC1,countC], function(cur,prev){
                console.log(`Composition API watch : ${prev}==>${cur}`);
            }
        )
        watch(
            countC, function(cur,prev){
                console.log(`Composition API watch : ${prev}==>${cur}`);
            },{immediate:true} //prev값 undefined
        )
        //불필요한 변수를 감시하지 않고 콜백함수에서 참조되는 변수만 감시
        const stop = watchEffect( //watchEffect를 변수로 저장하고 변수를 실행시키면 종료함
            function(){
                console.log(`Composition API watchEffect called : ${countC1.value} `);
            },{flush:'post'} //pre -> DOM이 업데이트하기전에 함수 호출
                            //post -> DOM이 업데이트 된 후 함수 호출
        )
        const onStop = function(){
            state.value = '중지'
            stop()
        }
        return{ countC, countC1, state,onStop}
    }

}
// 그러면 어떨 때 computed를 어떨 때 watch를 쓰냐??

// computed는 템플릿 내의 값이 data와 종속되었을 경우 사용하는게 유리합니다.왜냐하면 같은 경우에 watch를 사용하면 중복 호출하거나, 코드가 복잡해주기 때문입니다. 또한 computed의 값은 캐싱되기 때문에, 리렌더링 됬을 때, 같은 값이 들어왔다면 연산하지 않습니다. 그에 반해 watch는 같은 값이여도 연산을 다시 합니다. 컴포넌트가 리렌더링이 많이 되나, 값이 바뀔일이 없다면 computed를 필히 써야합니다.

// watch는 지정한 값이 변경된 시점에서 내가 원하는 액션(api call, route.push())을 하기 원할 때 사용합니다.
</script>

<style>

</style>