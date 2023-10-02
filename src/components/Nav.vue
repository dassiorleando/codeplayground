<script setup lang="ts">
import { useToggle } from '@vueuse/core'
import { useDarkGlobal } from '../utils'

const isDark = useDarkGlobal()
const toggleDark = useToggle(isDark)
</script>

<template>
  <!-- Navbar -->
  <nav class="bg-white dark:bg-gray-900">
    <div class="px-6 py-4 mx-auto flex justify-between items-center">
      <div class="flex items-center justify-between">
        <div>
          <a
            class="text-2xl font-bold text-gray-900 dark:text-white lg:text-3xl hover:text-gray-700 dark:hover:text-gray-300"
            href="#"
          >Code Playground</a>
        </div>
      </div>

      <div class="flex justify-center lg:flex lg:mt-0 lg:-mx-2">
        <a
          class="mx-2 align-items-center relative text-gray-700 dark:text-gray-200 hover:text-gray-600 dark:hover:text-gray-300"
          href="https://www.numericaideas.com"
          target="_BLANK"
        >
          <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAGQAAABkCAYAAABw4pVUAAAABGdBTUEAALGPC/xhBQAAACBjSFJNAAB6JgAAgIQAAPoAAACA6AAAdTAAAOpgAAA6mAAAF3CculE8AAAABmJLR0QA/wD/AP+gvaeTAAAACXBIWXMAABcRAAAXEQHKJvM/AAAAB3RJTUUH5gEPFgwXXgd+0AAACHJJREFUeNrtnHuMXFUdxz93ZvYBZSnt0rK4RV67QO3Kqq1YGqBQjARqW9AImBQEtWqND2pVRCnUoMgWKEGT8jIqrpgSoC1NoBaUpyKPUi0BJaxQlK6t2gfbUnZ2OzOXP75nOnc2Emfuzpm5dzyfZLMzk3PPPed87/mdx/2dHzgcDofD4XA4HA6Hw+FwOBwOh8PhcDgcVcSzlfG83r78xwYgUeblPrAP8O+/qLNqjREoc8KUoar3B/uCJIErgVOBbBmX+8BPgXsBbDZKQITxwBnAKUAbsAfYCKwHNtsuRx7bgqRQo84LkcVm4ELgWVuNERDjZOAHSIzGQBIfeAX4EXAXkLEtSrmmpJocDSwD2qGo8SpCIL+TgF8AsygWA/TAHg/8BPisjXKMJMqCAMwElgIHWsr/YJP/cf8jXQsyvR+wXeGoCwJwMfAlwKvU0xnI5xTg9BIvOwK4YMT1FScOgjQCVwBnW2iMGcABZaYfY7OycRAE4FCgB3gfVFSUtjLTt2LPfALxEQSgC7gONUqleLvM9ENAxmYl4yQIwGzgcqChQr3kRTS1LZWXgd02Kxg3QRLAl4H5EN50BdYSjwCvlnhZGlhDeQvcUBWMG2OA76MZ0mjHk7+hNcZQCWlXAevA7oo9joKApqDLgCOhfFGWd/cw84ZVrLmoE3z/DjRh2PMuybPAauCKgfbWt2Zev4rl3T3WKhZXQUDbHdcAB4XN4Kbunlmn37Bq0hsf7rgGz/s0avjXgR3AVuBJ4OvDY5ovPfPauwfmLrrjTDxSNitlNfMqcCHwV6BnXm9fLoQpOc33vDnzz+9ZcvD2nQ/f+FzP+iM2bj2sIb3vkFwqMTjQNnbrdSfPTT///rO6Mo0NV5lrHrdZobgL0gB8C81+Vs/r7Qtj3z+E563cPaH10QXnLFuXyGRfTGRyb/pJrzWXSp60ofvsWcA5aE/tftsVirsgAOPQbuxrwKaQorQAc4E5uVRyMJdKppHYB6JXCFUjzmNIkOPRwDxxlPl4SITxSKSqigH1IwjAx4DvAU22t8htUk+CeMAC4FKw/97CFvUkCGjn9ir0simWokRVkBxycgjD4WjR2AHxEyWqguwCeoHBkNdPBX4IjK11RcolqoL4wG3AnaPI45PAIiAZp14SVUE8YC/aRAy7Mk4ClwGfgviYrqgKki/bNuDbaNEXhrHIvWcaxEOUKAuS51nk8RH2xdCxaJB/D0RflDgIAnAPcDPhXw6dgabD5Tg01ITIC2L2pTLAcvSSKCyXAF8AvMe/+YlaV+tdibwgAd5EWyMbQ17fBHyX0v2wakIsBAns3vahQX5byKwmIt+qyBILQaBIlN+hN4XpkFlZczCvBLERBIpE+Rk6rlB3xEoQ2C9KGq0vHhpldk21rs9IYidIgH8hp7lXyr6y4BrXUutKjCSWggRM15/RzGlXrctUKWIpCBSJsga4Ecs+t9UitoLAflGywI+BlbUuTyWItSAB9gBLgKdrXZDREntBAqbrdbRo3FLrMo2G2AsCRaI8ic4MlnvuIzLUhSBQJEovcAvlnfuIDHUjCOwXZRidtHqg1uUJQ10JEmA78B3gpVoXpFzqTpCA6XoJibK91mUqh7oTBIpEeQCZr+Fal6lU6lIQ2C+KD9wK/KrW5SmVuhUkwF7gajQljjx1LUjAdG1Bi8Y3cC+oaktAlKfR9sruKC9R6l4QKBLlbuDepj1hXYbtUw9H2koi8Kax3+ax5tHyf9FD4oQTJGLYNlk5YAXwG/O5VNJAfxXq/2sUgKaUsiWQ03c59XDEHdtRSSegOFe/Nz9PQ+++t6E1QRuKV9ICbEDuol0oFmIrhdhYW5HLznhz/QbUuxPm+zQKxxceBiah+Ii/7Vr91N7WV7cdCbwXHXk+HD3lz6OgMzNMO2SBR9He11mo57yGgqZNM2ly6LzKP76x6XIr7WbbZHWhU1AXm0b8KvJAv9MIMhmFWzoKeSOuBRajsH5TTSMC/AWJ226+PwM8h85/dFBwD/0T8EfkWL0Y+PjguIOeQJFHP4dcSbtN2qfQ6n0x2uvyzXV/N+W7HXm0LEWnsfJOFAuRo14sBfFQcJhFwFfQqaaRRwKaUA+Zic6CTEfuPZuBa1Gv8YGvoTAaGbTqPgGF/tuBTkllgAFzjw+i3d7TksOZJ8x9GoB/A59HbkNfNOl+jsa4NBL5MyhUxxTUm8YANyE/sH1YjnVie5aVRL64h6BAMf9tQPRMY34EHWduN98nIW/3+eh9uWfyGYcepJz5/AI6prDWNNZRqIetAKbed9v5jfi+b65/C5m0NcAmk99s5AXZhgSdjnqHD3QiU3YJeqgWIpGsUY0e0o8O3CxFT/sA6iUJ8z8J/NM0zgL0dGaQLX8E2fFBNNasMOkfQza+E/WuZgpHqaejUBuzgROPW99/TCKby+VSyXx5Gs1fi2nsZ4A/IGGPphCb9wTUg25GEYdyKGT6FApjYuwEwTT8WuBcFAWuHx3mXIhsej6O4RbTiHehJ/8A0yjHoDFiCzraNgc96TuQvT8VmZws6kkTgZ1ofMmkhvbN8Hx/l2nQduCXRrgJ6KxJp2nkKehByBqxdgIfRWNUh/m9Dcsh/mwLsh094WngeuQNsg7NnsYC/0EObh1o0O8zAnWgGdFkk08fGoTXohiJC02eD5p055l0bWicuMzc9zwvlzs225jqw+cFNEs7EZmjlSavyahXZE15lwD3oQnFlSbP/GxvMyYWvS1sT3sTaDAdMvdqQjOaZmR6csgcNVCY6eSnsykK0Xiy5m+IgqnLmvRZChMFP5CnDyT9RKJx+q0PDjfvfrvBlCH/EOZ3GIOTDN/8njVpm839EoFyDAK+rWmvw+FwOBwOh8PhcDgcDofD4XA4HA6Hw+FwOCLDO5Q3Ihw6t6jzAAAAJXRFWHRkYXRlOmNyZWF0ZQAyMDIyLTAxLTE1VDIyOjEyOjIzLTA1OjAw3tJJqwAAACV0RVh0ZGF0ZTptb2RpZnkAMjAyMi0wMS0xNVQyMjoxMjoyMy0wNTowMK+P8RcAAAAASUVORK5CYII=" style="width: 30px;">
        </a>
        <a
          class="mx-2 align-items-center relative text-gray-700 dark:text-gray-200 hover:text-gray-600 dark:hover:text-gray-300"
          href="#"
          @click.prevent="toggleDark()"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              v-if="isDark"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"
            />
            <path
              v-else
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
            />
          </svg>
        </a>
      </div>
    </div>
  </nav>
</template>

<style>
nav {
  height: var(--nav-height);
}
</style>
