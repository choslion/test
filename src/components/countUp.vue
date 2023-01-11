<template>
  <div>
    <h2>{{ clickCount }}</h2>
    <h2 v-if="clickCount <= 10 && clickCount >= 0">10과 같거나 작습니다.</h2>
    <h2 v-else-if="clickCount > 10">10보다 큽니다.</h2>
    <h2 v-else-if="clickCount < 0">음수입니다.</h2>
    <button v-on:click="clickUp()">클릭하면 숫자가 올라갑니다.</button>
    <button v-on:click="clickDown()">클릭하면 숫자가 내려갑니다.</button>
    <h2>{{ counter1 }}</h2>
    <button @:click="addCount1">2번째 클릭하면 숫자가 올라갑니다.</button>
    <button @:click="downCount1">2번째 클릭하면 숫자가 내려갑니다.</button>
    <select v-model="selectS">
      <option>수성</option>
      <option>금성</option>
      <option>지구</option>
      <option>화성</option>
      <option>목성</option>
    </select>
    <h2>{{ selectS }}</h2>
    <div>
      <img
        v-if="selectS === '수성'"
        src="https://w.namu.la/s/aaa9b59d8bbb82434067bb2d550b39f0ba7018eb27cd67a6e0b7bb0351ff9f5a0c677565d1c21264d7aa269acd1d845041adb5658e706dab5b3078996b7d99166249a76bb6fb6d695f60e9d95e58f8cf98f7a353bcc66f4ebacdd6b5456e1a49ea1f8044b4d91a57bd92e2ae27ba5e23"
        alt="수성"
      />
      <img
        v-if="selectS === '금성'"
        src="https://w.namu.la/s/5a813c6a603ca64263a401549671096359b8307fd8b3463d5ebc5d63956bde0d731dcef69fd5746d05ff9127464c922d4799556a6e75f8f667a39001357df14c0fd51fa6ca33a419dd46cd63f8c3af933dff81f6892ac350a51cee5e2e8aad49ed69c139f60cd7a64d41aa20df85533f"
        alt="금성"
      />
      <img
        v-if="selectS === '지구'"
        src="https://w.namu.la/s/8cdfe84a39fff7c8504c0235b9930eb7621066c584fae34ee6863c02f867c4e1c84e641c19a85dd7a64f0e65ac24701859f6f054f8a0b8891030fcae50b11f82bf5220cbaeb2fe712b89f97f571ced430c9c3049c7a70daeb51d60bae0cf483d0a12f204f35ac2234557967910ba829f"
        alt="지구"
      />
      <img
        v-if="selectS === '화성'"
        src="https://w.namu.la/s/9ec17f62b4f699172e55f4ce254b2b88837b9e12313ed189b9e560e61f87697c6d78aa90ce57253e055ab11bc3ef23757878511dc605b3282d201f55d95a32d3118587b10fa7961a382e050eae1a5aeb8ae7b7bbaaf676d2945037c259a3af504385ca1e086b8cbbc99da2f5f2351455"
        alt="화성"
      />
      <img
        v-if="selectS === '목성'"
        src="https://w.namu.la/s/6b6c2e2f6e0f590dce540028c5f15b50cef0636d9d48f3c5f39d6cd9d3c7db329a8f23ebe0615d7ceafab6a2586910c7d61e54e50ae31c6f83eed8354748eb65b65cc7e372ccaff02dc0487ef860ecdaaff715f16c1930c5b306dab9c52ea4d3ef2f51b71aaf853e2dfd777d8b8e4666"
        alt="목성"
      />
    </div>
    <ul>
      <li v-for="star in stars" :key="star">{{ star }}</li>
    </ul>
    <!-- <h2 v-for="(star, index) in stars" :key="index">{{ star }}</h2> -->
  </div>
</template>
<script>
import { ref, reactive } from 'vue';
export default {
  name: 'countUpHi',
  props: {
    hello: String,
  },
  data() {
    return {
      counter1: 0,
      selectS: '행성을 선택해주세요.',
    };
  },
  methods: {
    addCount1: function () {
      this.counter1++;
    },
    downCount1: function () {
      this.counter1--;
    },
  },
  setup() {
    const stars = reactive({
      1: '물병자리',
      2: '물고기자리',
      3: '양자리',
      4: '황소자리',
      5: '쌍둥이자리',
    });
    let clickCount = ref(0);
    const clickUp = function () {
      return clickCount.value++;
    };
    const clickDown = function () {
      return clickCount.value--;
    };

    // const inform = function () {
    //   if (clickCount < 10) {
    //     ref(console.log('10보다 작습니다.'));
    //   }
    // };
    return {
      clickCount,
      clickUp,
      clickDown,
      stars,
    };
  },
};
</script>
<style scoped></style>
