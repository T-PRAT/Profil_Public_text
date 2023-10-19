<template>
  <main class="w-full bg-blanc text-center text-bleu-fonce font-mono">
    <div class="container border mx-auto my-24 p-8 rounded bg-gris max-w-5xl">
      <h1 class="text-4xl font-bold">Les jobs</h1>
      <div class="text-left">
        Il y a <b>{{ count }}</b> annonces
      </div>
      <div class="grid grid-cols-1 justify-center" v-for="job in jobs">
        <JobCard :key="job.id" :job="job" />
      </div>
    </div>
  </main>
</template>

<script setup>
const { data: res } = await useFetch(
  "https://app.staging.profilpublic.fr/api/jobs"
);
const jobs = res.value.data;
const count = jobs.length;
</script>
