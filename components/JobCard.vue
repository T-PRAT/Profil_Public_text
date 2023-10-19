<script>
export default {
  props: {
    job: {
      type: Object,
      required: true,
    },
  },
};
</script>

<template>
  <div class="border border-bleu-fonce rounded p-4 my-4 bg-blanc">
    <h3 class="text-xl font-bold">{{ job.title }}</h3>
    <div class="text-left text my-2">
      <p class="indent-6" v-html="job.crushes"></p>
    </div>
    <div class="flex justify-between">
      <span class="flex bg-bleu-clair/50 p-1 rounded-xl">
        <p class="text-sm">
          Posté le :<b>{{ job.submittedAt }}</b>
        </p>
      </span>
      <span class="bg-gris p-1 rounded-xl">vue: {{ job.viewCount }}</span>
      <span class="bg-bleu-clair/50 p-1 rounded-xl">
        Contrat :
        {{ job.privateContract ? job.privateContract : "n/a" }}
      </span>
    </div>
  </div>
</template>
