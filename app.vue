<template>
  <div class="wrap">
    <div class="left">
      <div class="left-head head">
        Выбранно
        <ul class="list" v-auto-animate>
          <li class="list-item" v-for="item in leftValue" :key="item">
            <div class="list-box">
              {{ item }}
            </div>
          </li>
        </ul>
        Количество вещей {{ leftValue.length }}
      </div>
      <div class="labels">
        <label class="label" v-for="item in LEFT_ARR" :key="item.id">
          <input
            type="checkbox"
            :disabled="leftValue.length > 5 && leftValue.indexOf(item.name) === -1"
            name="things"
            :value="item.name"
            v-model="leftValue"
          />
          {{ item.name }}
        </label>
      </div>
    </div>
    <div class="right">
      <div class="right-head head">Выбранный элемент {{ rightValue }}</div>
      <div class="labels">
        <label class="label" v-for="item in RIGHT_ARR" :key="item.id">
          <input type="radio" name="things" :value="item.name" v-model="rightValue" />
          {{ item.name }}
        </label>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
  const leftValue = ref<string[]>([]);
  const rightValue = ref("");

  const LEFT_ARR = ref([
    {
      id: 1,
      name: "Shoes 1",
    },
    {
      id: 2,
      name: "Shoes 2",
    },
    {
      id: 3,
      name: "Shoes 3",
    },
    {
      id: 4,
      name: "Shoes 4",
    },
    {
      id: 5,
      name: "T-shirt 1",
    },
    {
      id: 6,
      name: "T-shirt 2",
    },
    {
      id: 7,
      name: "T-shirt 3",
    },
    {
      id: 8,
      name: "T-shirt 4",
    },
  ]);

  const RIGHT_ARR = ref([
    {
      id: 11,
      name: "Jacket 1",
    },
    {
      id: 12,
      name: "Jacket 2",
    },
    {
      id: 13,
      name: "Jacket 3",
    },
    {
      id: 14,
      name: "Jacket 4",
    },
    {
      id: 15,
      name: "Hoodie 1",
    },
    {
      id: 16,
      name: "Hoodie 2",
    },
    {
      id: 17,
      name: "Hoodie 3",
    },
    {
      id: 18,
      name: "Hoodie 4",
    },
  ]);
</script>

<style>
  *,
  *::before,
  *::after {
    box-sizing: border-box;
  }

  body {
    margin: 0;
    font-family: sans-serif;
    height: 100svh;
  }

  #__nuxt {
    height: 100%;
  }

  .wrap {
    display: flex;
    gap: 1.25rem;
    padding: 1.25rem;
    height: 100%;
  }

  .head {
    margin-bottom: 1.25rem;
    border: 0.0625rem solid #000;
    border-radius: 0.5rem;
    max-width: 18.75rem;
    padding: 1.25rem;
    border-radius: 0.25rem;
  }

  .right,
  .left {
    flex: 1;
    display: flex;
    flex-direction: column;
  }

  .right {
    align-items: flex-end;
  }
  .labels {
    margin-top: auto;
    width: 100%;
    padding: 0.625rem;
    border: 1px solid black;
    border-radius: 0.5rem;
  }
  .label {
    padding: 0.375rem;
    cursor: pointer;
    display: block;
    border: 1px solid black;
    border-radius: 0.5rem;
  }
  .label + .label {
    margin-top: 1.25rem;
  }

  .list {
    list-style-type: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-wrap: wrap;
    gap: 1.25rem;
    margin: 0.625rem 0;
  }

  .list-box {
    padding: 0.25rem 0.5rem;
    border: 1px solid black;
    border-radius: 0.5rem;
  }
</style>
