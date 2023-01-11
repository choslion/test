<template>
  <div>
    <h2 v-for="(season, index) in seasons" :key="index">{{ season.month }}는 {{ season.season }} 입니다.</h2>
    <ul>
      <li v-for="limited in limitS" :key="limited">{{ limited.month }}는 {{ limited.season }} 입니다.</li>
    </ul>
  </div>
</template>
<script>
import { reactive, computed } from 'vue';
export default {
  name: 'obHi',
  setup() {
    const seasons = reactive([
      { id: 1, month: '3,4,5', season: 'spring' },
      { id: 2, month: '6,7,8,9', season: 'summer' },
      { id: 3, month: '9,10,11', season: 'fall' },
      { id: 4, month: '12,1,2', season: 'winter' },
    ]);
    const limitS = computed(() => {
      return seasons.filter((item) => item.id < 3);
    });

    return {
      seasons,
      limitS,
    };
  },
};
</script>
