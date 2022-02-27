<template>
  <h1 @click="increase">    <!-- h1 태그를 클릭하면 increase 함수가 실행됨 -->
    {{ count }}             <!-- JavaScript에서 오는 데이터라는 의미로 {{ }} 사용 -->
  </h1>
  <div v-if="count > 4">    <!-- count가 4보다 크면 출력 -->
    4보다 큽니다!
  </div>
  <ul>
    <!-- fruits의 item을 fruit라는 변수에 할당하여 데이터로써 활용 -->
    <Fruit 
      v-for="fruit in fruits" 
      :key="fruit"
      :name="fruit">
      {{ fruit }}
    </Fruit>
  </ul>
</template>

<script>
import Fruit from '~/components/Fruit'    // 1. component 가져오기
export default {    // 객체 리터럴을 기본으로 내보내기
  components: {                           // 2. component 등록
    //Fruit: Fruit                        // 3. Fruit라는 component를 Fruit라는 이름으로 활용
    Fruit                                 // 속성과 데이터의 이름이 같으면 :뒤는 생략 가능
  },
  data() {    // data(): function() { 과 동일
    return {  // 객체 데이터를 반환
      count: 0,
      fruits : ['Apple', 'Banana', 'Cherry']
    }
  },
  methods: {
    increase() {    // 함수 생성
      // this는 script(태그) 부분을 지칭
      this.count += 1;
    }
  }

}
</script>

<style lang="scss">   // scss 문법으로 해석
 h1 {
   font-size: 50px;
   color: yellowgreen;
 }
 ul {
   li {
     font-size: 40px;
   }
 }
</style>
