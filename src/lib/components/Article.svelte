<script lang="ts">
  import PlainText from '$lib/components/PlainText.svelte';
  import RichText from '$lib/components/RichText.svelte';
  import { formatDate } from '$lib/util';

  export let title: string = '',
    content: string = '',
    published_at: Date | undefined = undefined;
</script>

<div>
  <div class="max-w-screen-md mx-auto px-6">
    <div class="pt-12 sm:pt-24">
      {#if !!published_at}
        <div class="font-bold text-sm">{formatDate('published_at', 'it')}</div>
      {:else}
        <div class="font-bold text-sm">DRAFT</div>
      {/if}
    </div>
    <h1 class="text-3xl md:text-5xl font-bold pt-1">
      <PlainText bind:content={title} />
    </h1>
  </div>
</div>

<div class="max-w-screen-md mx-auto px-6 pb-12 sm:pb-24">
  <div id="article_content" class="prose sm:prose-xl">
    <RichText bind:content />
  </div>
</div>
