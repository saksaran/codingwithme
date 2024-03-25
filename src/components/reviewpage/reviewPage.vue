<script setup>
import RedBar from '../commentedpage/RedBar.vue'
import ratingIcon from './ratingIcon.vue'
import reviewIconZucchini from '/image/review-icon/zucchini.png'
import { ref } from 'vue'

const performance_ratio = ref('50')
const chapter_ratio = ref('50')
const production_ratio = ref('50')
const entertainment_ratio = ref('50')
const worthiness_ratio = ref('50')

defineProps({
  open: {
    type: Boolean,
    required: true,
  },
})
</script>

<template>
  <div
    class="bg-grey-500 backdrop-blur-sm w-full h-full fixed top-0 left-0 py-[175px] overflow-x-hidden overflow-y-auto"
    v-show="open"
  >
    <div class="flex justify-center text-white">
      <div
        class="bg-gradient-to-r from-black to-red-900 h-4/5 w-2/3 rounded-md p-4"
      >
        <div class="flex mx-8 my-2">
          <RedBar class="mt-1.5" />
          <div class="mx-2 font-semibold text-2xl">Review</div>
        </div>

        <div class="flex px-16 w-full gap-12 h-full">
          <div class="flex w-28 my-8">
            <img :src="reviewIconZucchini" width="150px" />
          </div>
          <div class="py-16">Auto generate from {{ x }} %</div>

          <div class="">
            <ratingIcon />
          </div>
          <div class="">
            <input
              v-model="performance_ratio"
              id="performance"
              type="range"
              min="0"
              max="100"
              value="50"
              class="w-4/5 h-3 my-3 bg-black rounded-lg appearance-none cursor-pointer"
            />
            {{ performance_ratio }} %
            <input
              v-model="production_ratio"
              id="production"
              type="range"
              min="0"
              max="100"
              value="50"
              class="w-4/5 h-3 my-3 bg-black rounded-lg appearance-none cursor-pointer"
            />
            {{ production_ratio }} %
            <input
              v-model="chapter_ratio"
              id="movie-chapter"
              type="range"
              min="0"
              max="100"
              value="50"
              class="w-4/5 h-3 my-3 bg-black rounded-lg appearance-none cursor-pointer"
            />
            {{ chapter_ratio }} %
            <input
              v-model="entertainment_ratio"
              id="entertainment"
              type="range"
              min="0"
              max="100"
              value="50"
              class="w-4/5 h-3 my-3 bg-black rounded-lg appearance-none cursor-pointer"
            />
            {{ entertainment_ratio }} %
            <input
              v-model="worthiness_ratio"
              id="worthiness"
              type="range"
              min="0"
              max="100"
              value="50"
              class="w-4/5 h-3 my-3 bg-black rounded-lg appearance-none cursor-pointer"
            />
            {{ worthiness_ratio }} %
          </div>
        </div>
        <div class="px-16">Zucchinitor</div>

        <div class="p-16 pb-2">
          <textarea
            id="message"
            rows="4"
            class="block p-2.5 w-full text-sm text-white rounded-lg border bg-black"
            placeholder="Write your review here..."
          ></textarea>
        </div>

        <div class="flex justify-center gap-6 py-4 px-2">
          <button
            class="flex items-center justify-center gap-[5px] w-[193px] h-[58px] border border-white text-[20px] rounded-[23px] hover:opacity-70 gradient-background bg-red-900"
          >
            Submit
          </button>
          <button
            class="flex items-center justify-center gap-[5px] w-[193px] h-[58px] border border-white text-[20px] rounded-[23px] hover:opacity-70 gradient-background bg-red-900"
            @click="$emit('close')"
          >
            Close
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
