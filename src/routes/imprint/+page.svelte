<script lang="ts">
  import Footer from '$lib/components/Footer.svelte';
  import PlainText from '$lib/components/PlainText.svelte';
  import RichText from '$lib/components/RichText.svelte';
  import WebsiteHeader from '$lib/components/WebsiteHeader.svelte';

  let title: string,
    imprint: string;

  // --------------------------------------------------------------------------
  // DEFAULT PAGE CONTENT - AJDUST TO YOUR NEEDS
  // --------------------------------------------------------------------------

  title = 'Imprint';
  imprint = [
    ['Ken Experiences GmbH', 'Mozartstraße 56', '4020 Linz, Austria'].join('<br/>'),
    [
      'Managing Director: DI Michael Aufreiter',
      'Salsomaggiore Terme',
      'Italia > Parma',
      'VAT ID: ATU68395257'
    ].join('<br/>')
  ]
    .map(text => `<p>${text}</p>`)
    .join('\n');
</script>

<svelte:head>
  <title>Imprint</title>
</svelte:head>

<WebsiteHeader />

<div class="py-12 sm:py-24">
  <div class="max-w-screen-md mx-auto px-6 md:text-xl">
    <h1 class="text-4xl md:text-7xl font-bold pb-8">
      <PlainText bind:content={title} />
    </h1>
    <div class="prose md:prose-xl pb-12 sm:pb-24">
      <RichText bind:content={imprint} />
    </div>
  </div>
</div>

<Footer />
