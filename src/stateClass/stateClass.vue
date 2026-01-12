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

  <div class="flex flex-col space-y-4">
    <!-- 商品列表的父容器 -->

    <!-- 第一个商品项 -->
    <div class="group border p-4">
      商品 1
      <div class="hidden group-[&:nth-of-type(3)]:block text-green-600 font-bold">
        🎉 独家优惠！
      </div>
    </div>

    <!-- 第二个商品项 -->
    <div class="group border p-4">
      商品 2
      <div class="hidden group-[&:nth-of-type(3)]:block text-green-600 font-bold">
        🎉 独家优惠！
      </div>
    </div>

    <!-- 第三个商品项 (关键！这个会触发效果) -->
    <div class="group border p-4">
      商品 3
      <div class="hidden group-[&:nth-of-type(3)]:block text-green-600 font-bold">
        🎉 独家优惠！
      </div>
    </div>

    <!-- 第四个商品项 -->
    <div class="group border p-4">
      商品 4
      <div class="hidden group-[&:nth-of-type(3)]:block text-green-600 font-bold">
        🎉 独家优惠！
      </div>
    </div>

  </div>
<!-- 隐式组(Implicit groups)  in-* 变体响应任何父级的状态变化，因此如果你想要更细粒度的控制，则需要使用 group。-->
  <div tabindex="0">
    <div class="opacity-50 in-focus:opacity-100">
      <div class="w-20 h-20 bg-blue-300"></div>
    </div>
  </div>
<!-- 基于兄弟状态的样式(Styling based on sibling state)  请使用 peer 类标记兄弟元素
      peer 标记只能用于先前的兄弟元素
 -->
  <form>
    <label class="block">
      <span class="...">Email</span>
      <input type="email" class="peer ..." />
      <p class="invisible peer-invalid:visible ...">Please provide a valid email address.</p>
    </label>
  </form>

<!-- 区分兄弟元素  使用多个对等点时，你可以通过使用 peer/{name} 类为该对等点指定唯一名称，并使用 peer-checked/{name} 等类将该名称包含在变体中 -->
  <fieldset>
    <legend>Published status</legend>
    <input id="draft" class="peer/draft" type="radio" name="status" checked />
    <label for="draft" class="peer-checked/draft:text-sky-500">Draft</label>
    <input id="published" class="peer/published" type="radio" name="status" />
    <label for="published" class="peer-checked/published:text-sky-500">Published</label>
    <div class="hidden peer-checked/draft:block">Drafts are only visible to administrators.</div>
    <div class="hidden peer-checked/published:block">Your post will be publicly visible on your site.</div>
  </fieldset>

<!-- 任意同行 你可以通过在方括号之间提供自己的选择器作为 任意值 来动态创建一次性 peer-* 变体： -->
  <form>
    <label for="email">Email:</label>
    <input id="email" name="email" type="email" class="is-dirty peer" required />
    <div class="peer-[.is-dirty]:peer-required:block hidden">This field is required.</div>
    <!-- ... -->
  </form>

<!-- 伪元素 -->
  <label>
    <span class="text-gray-700 after:ml-0.5 after:text-red-500 after:content-['*'] ...">Email</span>
    <input type="email" name="email" class="..." placeholder="you@example.com" />
  </label>

<!-- 使用这些变体时，Tailwind 会默认自动添加 content: '' -->
  <blockquote class="text-center text-2xl font-semibold text-gray-900 italic dark:text-white">
    When you look
    <span class="relative inline-block before:absolute before:-inset-1 before:block before:-skew-y-3 before:bg-pink-500">
    <span class="relative text-white dark:text-gray-950">annoyed</span>
  </span>
    all the time, people think that you're busy.
  </blockquote>

<!-- ::placeholder  使用 placeholder 变体设置任何输入或文本区域的占位符文本的样式： -->
  <input
      class="placeholder:text-gray-500 placeholder:italic ..."
      placeholder="Search for anything..."
      type="text"
      name="search"
  />

<!-- ::file   样式使用 file 变体设置文件输入中的按钮： -->
  <input
      type="file"
      class="file:mr-4 file:rounded-full file:border-0 file:bg-violet-50 file:px-4 file:py-2 file:text-sm file:font-semibold file:text-violet-700 hover:file:bg-violet-100 dark:file:bg-violet-600 dark:file:text-violet-100 dark:hover:file:bg-violet-500 ..."
  />

<!-- ::marker  使用 marker 变体设置列表中的计数器或项目符号的样式： -->
  <div>
    <ul role="list" class="list-disc marker:text-sky-400 pl-6">
      <li>5 cups chopped Porcini mushrooms</li>
      <li>1/2 cup of olive oil</li>
      <li>3lb of celery</li>
    </ul>
  </div>

<!--::selection  使用 selection 变体设置活动文本选择样式：  -->
  <div class="selection:bg-fuchsia-300 selection:text-fuchsia-900">
    <p>
      So I started to walk into the water. I won't lie to you boys, I was terrified. But I pressed on, and as I made my
      way past the breakers a strange calm came over me. I don't know if it was divine intervention or the kinship of all
      living things but I tell you Jerry at that moment, I <em>was</em> a marine biologist.
    </p>
  </div>

<!-- ::first-line 和 ::first-letter(::first-line and ::first-letter)  -->
  <div class="text-gray-700">
    <p
        class="first-letter:float-left first-letter:mr-3 first-letter:text-7xl first-letter:font-bold first-letter:text-gray-900 first-line:tracking-widest first-line:uppercase"
    >
      Well, let me tell you something, funny boy. Y'know that little stamp, the one that says "New York Public Library"?
    </p>
    <p class="mt-6">Well that may not mean anything to you, but that means a lot to me. One whole hell of a lot.</p>
  </div>

<!-- ::backdrop 使用 backdrop 变体设置 原生 <dialog> 元素 的背景样式 -->
  <dialog class="backdrop:bg-gray-50">
    <form method="dialog">
      <!-- ... -->
    </form>
  </dialog>

<!-- 媒体和特性查询  根据视口来设置元素的样式-->
  <div class="grid grid-cols-3 md:grid-cols-4 lg:grid-cols-6 gap-2">
    <div v-for="i in 6" class="w-20 h-20 bg-blue-500"></div>
  </div>

<!-- 要根据父元素的宽度而不是视口来设置元素的样式，请使用 @md 和 @lg 等变体： -->
  <div class="@container w100 mt-20" >
    <div class="flex flex-col @md:flex-row">
      <div v-for="i in 6" class="w-20 h-20 bg-blue-500"></div>
    </div>
  </div>

<!-- prefers-color-scheme 媒体查询告诉你用户喜欢浅色主题还是深色主题，通常在操作系统级别配置。 -->
  <div class="bg-white dark:bg-gray-900 ...">
    <!-- ... -->
    <h3 class="text-gray-900 dark:text-white ...">Writes upside-down</h3>
    <p class="text-gray-500 dark:text-gray-400 ...">
      The Zero Gravity Pen can be used to write in any orientation, including upside-down. It even works in outer space.
    </p>
  </div>

<!-- prefers-reduced-motion 媒体查询会告诉你用户是否已请求你尽量减少不必要的动作。 -->
  <button type="button" class="bg-indigo-500 ..." disabled>
    <svg class="animate-spin motion-reduce:hidden ..." viewBox="0 0 24 24"><!-- ... --></svg>
    Processing...
  </button>

<!-- prefers-contrast 媒体查询告诉你用户是否请求了更多或更少的对比度。 -->
  <label class="block">
    <span class="block text-sm font-medium text-gray-700">Social Security Number</span>
    <input
        class="border-gray-200 placeholder-gray-400 contrast-more:border-gray-400 contrast-more:placeholder-gray-500 ..."
    />
    <p class="text-gray-600 opacity-10 contrast-more:opacity-100 ...">We need this to steal your identity.</p>
  </label>

<!-- forced-colors 媒体查询指示用户是否使用强制颜色模式。这些模式使用用户定义的文本、背景、链接和按钮调色板覆盖站点的颜色。 -->
  <label>
    <input type="radio" class="appearance-none forced-colors:appearance-auto" />
    <p class="hidden forced-colors:block">Cyan</p>
    <div class="bg-cyan-200 forced-colors:hidden ..."></div>
    <div class="bg-cyan-500 forced-colors:hidden ..."></div>
  </label>

<!-- 使用 inverted-colors 变体在用户启用了反转配色方案时有条件地添加样式： -->
  <div class="shadow-xl inverted-colors:shadow-none ...">
    <!-- ... -->
  </div>

<!-- 指针和任意指针(pointer and any-pointer) pointer 媒体查询会告知你用户是否有主要指针设备（例如鼠标），以及该指针设备的精度。 -->
  <fieldset aria-label="Choose a memory option">
    <div class="flex items-center justify-between">
      <div>RAM</div>
      <a href="#"> See performance specs </a>
    </div>
    <div class="mt-4 grid grid-cols-6 gap-2 pointer-coarse:mt-6 pointer-coarse:grid-cols-3 pointer-coarse:gap-4">
      <label class="p-2 pointer-coarse:p-4 ...">
        <input type="radio" name="memory-option" value="4 GB" className="sr-only" />
        <span>4 GB</span>
      </label>
      <!-- ... -->
    </div>
  </fieldset>

<!-- orientation 使用 portrait 和 landscape 变体在视口处于特定方向时有条件地添加样式： -->
  <div>
    <div class="portrait:hidden">
      <!-- ... -->
    </div>
    <div class="landscape:hidden">
      <p>This experience is designed to be viewed in landscape. Please rotate your device to view the site.</p>
    </div>
  </div>

<!-- 使用 noscript 工具根据用户是否启用脚本（例如 JavaScript）有条件地添加样式： -->
  <div class="hidden noscript:block">
    <p>This experience requires JavaScript to function. Please enable JavaScript in your browser settings.</p>
  </div>

<!-- 使用 print 变体有条件地添加仅在打印文档时适用的样式： -->
  <div>
    <article class="print:hidden">
      <h1>My Secret Pizza Recipe</h1>
      <p>This recipe is a secret, and must not be shared with anyone</p>
      <!-- ... -->
    </article>
    <div class="hidden print:block">Are you seriously trying to print this? It's secret!</div>
  </div>

<!-- @supports 使用 supports-[...] 变体根据用户浏览器是否支持某项功能来设置样式： -->
  <div class="flex supports-[display:grid]:grid ...">
    <!-- ... -->
  </div>

<!-- 使用 starting 变体在元素首次渲染在 DOM 中或从 display: none 过渡到可见时设置元素的外观： -->
  <div>
    <button popovertarget="my-popover">Check for updates</button>
    <div popover id="my-popover" class="opacity-0 starting:open:opacity-0 ...">
      <!-- ... -->
    </div>
  </div>

<!-- 属性选择器  数据属性 -->
  <!-- Will apply -->
  <div data-active class="border border-gray-300 data-active:border-purple-500">
    <!-- ... -->
  </div>
  <!-- Will not apply -->
  <div class="border border-gray-300 data-active:border-purple-500">
    <!-- ... -->
  </div>

<!-- RTL 支持 -->
  <div class="group flex items-center">
    <div class="ltr:ml-3 rtl:mr-3">
      <p class="text-gray-700 group-hover:text-gray-900 ...">sssssssssssaaaaaaaaaaaaaaaaaaaaaaaaa</p>
      <p class="text-gray-500 group-hover:text-gray-700 ...">ggggggggggggggggggggggggggffffffffffffff</p>
    </div>
  </div>
<!-- 打开/关闭状态  使用 open 变体在 <details> 或 <dialog> 元素处于打开状态时有条件地添加样式： -->
  <details class="border border-transparent open:border-black/10 open:bg-gray-100 ..." open>
    <summary class="text-sm leading-6 font-semibold text-gray-900 select-none">Why do they call it Ovaltine?</summary>
    <div class="mt-3 text-sm leading-6 text-gray-600">
      <p>The mug is round. The jar is round. They should call it Roundtine.</p>
    </div>
  </details>

<!-- 设置惰性元素的样式 inert 变体允许你设置标有 inert 属性的元素样式： -->
  <form>
    <legend>Notification preferences</legend>
    <fieldset>
      <input type="radio" />
      <label> Custom </label>
      <fieldset inert class="inert:opacity-50">
        <!-- ... -->
      </fieldset>
      <input type="radio" />
      <label> Everything </label>
    </fieldset>
  </form>

<!-- 子选择器 虽然通常最好将工具类直接放在子元素上，但你可以在需要设置你无法控制的直接子元素样式的情况下使用 * 变体结束：
需要注意的是，直接在子规则本身上使用实用程序覆盖样式是行不通的，因为子规则是在常规规则之后生成的，并且它们具有相同的特殊性：
 -->
  <div>
    <h2>Categories</h2>
      <ul class="*:rounded-full *:border *:border-sky-100 *:bg-sky-50 *:px-2 *:py-0.5 dark:text-sky-300 dark:*:border-sky-500/15 dark:*:bg-sky-500/10 ...">
        <li>Sales</li>
        <li>Marketing</li>
        <li>SEO</li>
        <!-- ... -->
      </ul>
  </div>
<!-- 设置所有后代的样式 与 * 一样，** 变体可用于设置元素子元素的样式。主要区别在于 ** 将样式应用于所有后代，而不仅仅是直接子代-->
  <ul class="**:data-avatar:size-12 **:data-avatar:rounded-full ...">

  </ul>
</template>

<style scoped>

</style>