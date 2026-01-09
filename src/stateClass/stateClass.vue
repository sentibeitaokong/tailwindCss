<script setup lang="ts">

</script>

<template>
  <!-- 中等断点处、悬停时在夜间模式下更改背景颜色： -->
  <button class="dark:md:hover:bg-fuchsia-600">Save changes</button>
  <br/>
  <!-- 伪类 -->
  <button class="mt-5 bg-violet-500 hover:bg-violet-600 focus:outline-2 focus:outline-offset-2 focus:outline-violet-500 active:bg-violet-700 rounded-full px-5">
    Save changes
  </button>
<!--
:first、:last、:odd 和 :even(:first, :last, :odd, and :even)
使用 first 和 last 变体对元素作为第一个子元素或最后一个子元素进行样式化：
使用 nth-* 和 nth-last-* 变体根据子元素在列表中的位置设置子元素的样式
你还可以使用 odd 和 even 变体在元素为奇数或偶数子元素时设置其样式：

-->
<!--  <div class="nth-3:underline">
    &lt;!&ndash; ... &ndash;&gt;
  </div>
  <div class="nth-last-5:underline">
    &lt;!&ndash; ... &ndash;&gt;
  </div>
  <div class="nth-of-type-4:underline">
    &lt;!&ndash; ... &ndash;&gt;
  </div>
  <div class="nth-last-of-type-6:underline">
    &lt;!&ndash; ... &ndash;&gt;
  </div>-->

<!-- :required  :disabled :invalid -->
  <br/>
  <input
      type="text"
      value="tbone"
      disabled
      class="mt-5 invalid:border-pink-500 invalid:text-pink-600 focus:border-sky-500 focus:outline focus:outline-sky-500 focus:invalid:border-pink-500 focus:invalid:outline-pink-500 disabled:border-gray-200 disabled:bg-gray-200 disabled:text-gray-500 disabled:shadow-none dark:disabled:border-gray-700 dark:disabled:bg-gray-800/20"
  />
<!-- 使用 has-* 变体根据元素后代的状态或内容设置元素的样式： -->
  <br/>
  <label
      class="mt-5 has-checked:bg-indigo-50 has-checked:text-indigo-900 has-checked:ring-indigo-200 dark:has-checked:bg-indigo-950 dark:has-checked:text-indigo-200 dark:has-checked:ring-indigo-900 ..."
  >
    Google Pay
    <input type="radio" class="checked:border-indigo-500 ..." />
  </label>

<!--基于组的后代的样式  -->
  <div class="group ...">
    <h4 class="hidden group-has-[a]:block">Spencer Sharp</h4>
    <p>Product Designer at <a href="www.baidu.com">planeteria.tech</a></p>
  </div>
<!-- 基于同级的后代的样式 -->
  <div class="mt-10">
    <label class="peer ...">
      <input type="checkbox" name="todo[1]" checked />
      Create a to do list
    </label>
    <span class="peer-has-checked:hidden ml-5">x</span>
  </div>
<!--      :not()
  当与其他伪类变体结合使用时，它特别强大，例如将 not-focus: 与 hover: 结合起来，仅在元素未聚焦时应用悬停样式：
 -->
  <button class="bg-indigo-600 hover:not-focus:bg-indigo-700">
    save change
  </button>
<!--基于父状态的样式  -->
  <a href="#" class="group bg-blue-700">
    <div>
      <h3 class="text-gray-900 group-hover:text-blue-400">New project</h3>
    </div>
    <p class="text-gray-500 group-hover:text-blue-400">Create a new project from a variety of starting templates.</p>
  </a>

<!-- 嵌套组 -->
  <ul role="list">
    <li class="group/item ...">
      <div class="group/edit invisible group-hover/item:visible">
        <div class="group-hover/edit:text-gray-700">Call</div>
        <div class="group-hover/edit:translate-x-0.5 group-hover/edit:text-blue-500">222</div>
      </div>
    </li>
  </ul>
<!-- 任意组 -->
  <div class="group is-published">
    <div class="hidden group-[.is-published]:block">
      Published
    </div>
  </div>

  <div class="group">
    <div class="group-[:nth-of-type(3)_&]:invisible">
     1
    </div>
    <div>
      2
    </div>
    <div>
      3
    </div>
    <div>
      4
    </div>
  </div>
</template>

<style scoped>

</style>