---
title: Vue Component With the Fetch API
description: Get Data From an API in a Vue Component With the Fetch API
---

Hardly would you as a web developer build an app without getting data from some source. Sometimes from external sources or some part of your app.

Luckly, this is very easy when using the native [FETCH API](https://upmostly.com/tutorials/react-how-to-fetch-data-from-api) in javascript.

An the alternative is to use axios. Axios is a package that can be install in you app. Install Axios with 

```shell
npm i axios
```

---

## Fetch Data
First, we need to create a new Vue instance and define a variable. We’ll initialize it as an empty array, as we will add here all the information we retrieve from the JSON placeholder API:

```js
<script>
export default {
  data() {
    return {
      listItems: [],
    };
  },
```

Then, in our Methods section, we will create a method that will retrieve the data from the actual API. In this case, we’ll use the Async/Await syntax for added clarity:

```js

<script>
export default {
  data() {
    return {
      listItems: [],
    };
  },

  methods: {
    async getData() {
      const res = await fetch("https://api.github.com/users/safoah91/repos");
      const finalRes = await res.json();
      this.listItems = finalRes;
    },
  },

  mounted() {
    this.getData();
  },
};
</script>
```

As you’ve probably noticed, during the final step we’ve saved our API response directly in our previously generated variable. This means that the data is now available globally inside our component, and we can render it using the v-for syntax in our template:

```jsx
<template>
  <section class="bg-slate-100 py-32 px-28">
    <h2 class="text-4xl font-bold">My Repos</h2>
    <p class="text-slate-500">
      Lorem ipsum dolor, sit amet consectetur adipisicing elit.
    </p>
    <article class="mt-6 grid grid-cols-2 gap-6">
      <div
        class="shadow-lg py-4 px-8 rounded-lg"
        v-for="item in listItems"
        v-bind:key="item"
      >
        <div class="flex justify-between">
          <a
            :href="item.html_url"
            class="text-indigo-400 hover:text-indigo-600"
          >
            <p>{{ item.name }}</p>
          </a>
          <p
            class="
              capitalize
              text-sm
              border border-indigo-300
              text-indigo-400
              hover:bg-indigo-500 hover:text-white hover:cursor-pointer
              px-4
              py-1
              rounded-3xl
            "
          >
            {{ item.visibility }}
          </p>
        </div>

        <p class="my-6 text-slate-500">{{ item.description }}</p>
        <p class="text-slate-400 flex items-center gap-2">
          <span class="block w-4 h-4 bg-indigo-600 rounded-full"></span
          >{{ item.language }}
        </p>
      </div>
    </article>
  </section>
</template>
```

[Original source](https://upmostly.com/vue-js/get-data-from-an-api-in-a-vue-component-with-the-fetch-api)