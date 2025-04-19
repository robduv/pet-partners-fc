<template>
  <div
    class="mx-auto w-full max-w-7xl rounded-xl border border-surface-200 bg-surface-0 p-6 dark:border-surface-700 dark:bg-surface-900"
  >
    <div class="flex flex-col items-center justify-between gap-2 sm:flex-row">
      <div class="text-sm text-surface-600 dark:text-surface-400">
        © {{ new Date().getFullYear() }} Pet Partners of Fairfield County
      </div>
      <div class="flex gap-4">
        <a
          href="https://www.facebook.com/groups/322425249919492"
          target="_blank"
          rel="noopener noreferrer"
          class="text-sm text-surface-600 transition-colors hover:text-primary dark:text-surface-400"
        >
          <i class="pi pi-facebook text-xl"></i>
        </a>
      </div>
    </div>
  </div>
</template>
