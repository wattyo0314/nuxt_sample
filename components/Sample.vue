<template lang="html">
  <div>
    <h1>{{ title }}</h1>
    <div class="sample">
      こんにちは。{{ myName }} です。趣味は{{ hobby }}です。 名前を逆にすると{{
        reverseName
      }}です。ちなみに下の名前は{{ lastName }}です。年齢は{{ age }}歳です。
    </div>
    <button type="button" @click="plus">count</button>
    <p>
      {{ num
      }}<span :class="['hide', { multiple_of_three: num % 3 === 0 && num > 0 }]"
        >あほになる</span
      >
    </p>
    <button type="button" @click="doubleplus">doublecount</button>
    <div :class="['hide', { seven: num === 7 }]">
      ７回クリックされたよ
    </div>
    <div class="slot">
      <slot name="red" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myName: "渡邊佐資",
      hobby: "読書",
      num: 0
    };
  },
  props: {
    title: {
      type: String,
      default: "タイトルを記入してください"
    },
    age: {
      type: Number,
      default: 0
    }
  },
  methods: {
    plus() {
      this.num++;
    },
    doubleplus() {
      this.num += 2;
    }
  },
  computed: {
    reverseName() {
      return this.myName
        .split("")
        .reverse()
        .join("");
    },
    lastName() {
      return this.myName.slice(2, 4);
    }
  }
};
</script>

<style lang="scss" scoped>
.hide {
  display: none;
}
.seven {
  display: block;
}
.multiple_of_three {
  display: block;
}
.slot {
  color: red;
}
</style>
