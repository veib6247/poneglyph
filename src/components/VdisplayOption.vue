<script setup lang="ts">
  //
  const props = defineProps({
    linkTitle: {
      type: String,
      required: true,
    },

    hyperLink: {
      type: String,
      required: true,
    },
  })

  /**
   *
   */
  const copyToClipboard = () => {
    navigator.clipboard.writeText(props.hyperLink)

    console.info(`"${props.hyperLink}" has been copied to the clipboard`)
  }
</script>

<template>
  <div class="flex gap-2 place-content-center">
    <a :href="hyperLink" class="btn w-60 gap-2 rounded-lg glass" target="_blank">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="w-5 h-5">
        <path fill-rule="evenodd"
          d="M4.25 5.5a.75.75 0 00-.75.75v8.5c0 .414.336.75.75.75h8.5a.75.75 0 00.75-.75v-4a.75.75 0 011.5 0v4A2.25 2.25 0 0112.75 17h-8.5A2.25 2.25 0 012 14.75v-8.5A2.25 2.25 0 014.25 4h5a.75.75 0 010 1.5h-5z"
          clip-rule="evenodd" />
        <path fill-rule="evenodd"
          d="M6.194 12.753a.75.75 0 001.06.053L16.5 4.44v2.81a.75.75 0 001.5 0v-4.5a.75.75 0 00-.75-.75h-4.5a.75.75 0 000 1.5h2.553l-9.056 8.194a.75.75 0 00-.053 1.06z"
          clip-rule="evenodd" />
      </svg>

      {{ linkTitle }}
    </a>

    <button name="copyLinkButton" class="btn glass rounded-md btn-square" @click="copyToClipboard">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="w-5 h-5">
        <path fill-rule="evenodd"
          d="M13.887 3.182c.396.037.79.08 1.183.128C16.194 3.45 17 4.414 17 5.517V16.75A2.25 2.25 0 0114.75 19h-9.5A2.25 2.25 0 013 16.75V5.517c0-1.103.806-2.068 1.93-2.207.393-.048.787-.09 1.183-.128A3.001 3.001 0 019 1h2c1.373 0 2.531.923 2.887 2.182zM7.5 4A1.5 1.5 0 019 2.5h2A1.5 1.5 0 0112.5 4v.5h-5V4z"
          clip-rule="evenodd" />
      </svg>
    </button>
  </div>
</template>
