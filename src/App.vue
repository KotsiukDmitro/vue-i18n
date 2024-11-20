<script setup>
import { useI18n } from 'vue-i18n'

const { t, locale } = useI18n({ useScope: 'global' })

const switchLang = () => {    
  locale.value === 'en' ? locale.value = 'ua' : locale.value = 'en'
  localStorage.setItem('lang', locale.value)
}

</script>

<template>
  <div class="h-full grid place-items-center pt-20">
    <form class="border border-blue-500 rounded-md p-10 w-[500px] bg-slate-200">
      <div class="text-3xl text-blue-600 text-center mb-10">
        {{ $t('title') }}
      </div>
      <div>
        <input
          class="border border-gray-500 pl-3 rounded-md w-full mb-10 outline-none"
          type="text"
          name="userName"
          :placeholder="$t('placeholders.userName')"
        />
      </div>

      <div>
        <input
          class="border border-gray-500 pl-3 rounded-md w-full outline-none mb-10"
          type="password"
          name="password"
          :placeholder="$t('placeholders.password')"
        />
      </div>

      <div class="mb-10 cursor-pointer">
        <input id="cb" type="checkbox" name="remember me" />
        <label for="cb" class="ml-2">{{ $t('checkbox') }}</label>
      </div>

      <div class="text-center mb-10">
        <button
          class="border border-blue-400 px-5 pb-1 rounded-md text-xl font-bold text-blue-500 bg-white"
        >
          {{ $t('buttons.login') }}
        </button>
      </div>

      <div class="mb-10 text-red-400 underline hover:text-red-600">
        <a href="#">{{ $t('forgot') }}</a>
      </div>

      <div @click="switchLang" class="text-blue-600 cursor-pointer">{{ $t('language') }}</div>
    </form>
  </div>
</template>


