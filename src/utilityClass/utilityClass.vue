<script setup lang="ts">

</script>

<template>
  <div>
    <!-- 设置悬停和聚焦状态的样式    样式前面加状态属性
      .hover\:bg-sky-700 {
        &:hover {
          background-color: var(--color-sky-700);
        }
      }
     -->
    <button class="bg-sky-500 hover:bg-sky-700">hover</button>
    <br/>
    <button class="bg-sky-500 disabled:hover:bg-sky-500">hove and disabled</button>
    <!-- 栅格布局 sm节点以上 分成三栏   sm相当于width >= 40rem   -->
    <div class="grid grid-cols-2 sm:grid-cols-3 h-100 m-10">
      <div v-for="i in 6" class="flex justify-center items-center bg-blue-400 border-double w-20 h-20">
        {{i}}
      </div>
    </div>
    <!-- dark前缀  黑夜模式   -->
    <h3 class="text-gray-900 dark:text-white mt-5 text-base font-medium tracking-tight ">Writes upside-down</h3>
    <p class="text-gray-500 dark:text-gray-400 mt-2 text-sm ">
      The Zero Gravity Pen can be used to write in any orientation, including upside-down. It even works in outer space.
    <!--
       .dark\:bg-gray-800 {
          @media (prefers-color-scheme: dark) {
            background-color: var(--color-gray-800);
          }
        }
       -->
    </p>
    <!-- 使用任意值   -->
    <button class="bg-[#316ff6] mt-10">
      Sign in with Facebook
    </button>
    <div class="grid grid-cols-[24rem_2.5rem_minmax(0,1fr)]">
    </div>
    <div class="max-h-[calc(100dvh-(--spacing(6)))]">
    </div>

    <!-- 复杂选择器   -->
    <button class="dark:lg:data-current:hover:bg-indigo-600 ...">
      <!--
       @media (prefers-color-scheme: dark) and (width >= 64rem) {
          button[data-current]:hover {
            background-color: var(--color-indigo-600);
          }
        }
       -->
    </button>


     <!-- 管理重复   -->
    <div>
      <div class="flex items-center space-x-2 text-base">
        <h4 class="font-semibold text-slate-900">Contributors</h4>
        <span class="bg-slate-100 px-2 py-1 text-xs font-semibold text-slate-700 ...">204</span>
      </div>
      <div class="mt-3 flex -space-x-2 overflow-hidden">
        <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" src="https://images.unsplash.com/photo-1491528323818-fdd1faba62cc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
        <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" src="https://images.unsplash.com/photo-1550525811-e5869dd03032?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
        <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2.25&w=256&h=256&q=80" alt="" />
        <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
        <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" src="https://images.unsplash.com/photo-1517365830460-955ce3ccd263?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
      </div>
      <div class="mt-3 text-sm font-medium">
        <a href="#" class="text-blue-500">+ 198 others</a>
      </div>
    </div>
    <!--  使用组件  -->
    <!-- export function VacationCard({ img, imgAlt, eyebrow, title, pricing, url }) {
        return (
          <div>
            <img className="rounded-lg" src={img} alt={imgAlt} />
            <div className="mt-4">
              <div className="text-xs font-bold text-sky-500">{eyebrow}</div>
              <div className="mt-1 font-bold text-gray-700">
                <a href={url} className="hover:underline">
                  {title}
                </a>
              </div>
              <div className="mt-2 text-sm text-gray-600">{pricing}</div>
            </div>
          </div>
        );
      }
    -->
    <!-- 使用自定义 CSS   style.css里面添加自定义样式   -->
    <button class="btn-primary">Save changes</button>

    <!-- 冲突的工具类  会根据样式表定义最晚的类为标准  -->
<!--    <div class="grid flex">
      &lt;!&ndash; ... &ndash;&gt;
    </div>-->

    <!-- 使用前缀选项   -->
<!--    @import "tailwindcss" prefix(tw);
        @layer theme {
          :root {
            --tw-color-red-500: oklch(0.637 0.237 25.331);
          }
        }
        @layer utilities {
          .tw\:text-red-500 {
            color: var(--tw-color-red-500);
          }
        }


-->

  </div>
</template>

<style scoped>

</style>