<script lang="ts">
	// Types
	import type { PageProps } from "./$types";

	// Components
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import Pricing from "$lib/components/layout/Pricing.svelte";

	// Props
	const { data }: PageProps = $props();
</script>

<Pricing />

<Testimonials
  testimonials={[
    {
      name: "Casey Liu",
      position: "Head of AI",
      company: "Studio XYZ",
      quote: "We saw eval scores for user engagement leap by 39% after integrating Hume's Octave voices.",
      image: "/generated/image-a-professional-headshot-of-an-east-asian.webp"
    },
    {
      name: "Olivia Han",
      position: "Cofounder",
      company: "Ream Health",
      quote: "EVI made our conversational agent feel alive—expressive, intuitive, and emotionally aware.",
      image: "/generated/image-a-professional-headshot-of-a-white-woman.webp"
    },
    {
      name: "Martín Lehner",
      position: "Professor",
      company: "ETH Zurich",
      quote: "Hume’s API finally makes it possible to measure emotional state dynamically. Nothing else comes close.",
      image: "/generated/image-a-professional-headshot-of-a-black-man-i.webp"
    }
  ]}
/>

<CallToAction
  title="AI that understands you"
  subtitle="Build experiences powered by emotional intelligence"
  description="See the impact of empathic AI—voice interactions that actively listen, understand, and delight. Start building with models that put human well-being at the center."
  imageSrc="/generated/image-a-cheerful-developer-sitting-at-a-sleek-.webp"
  callsToAction={[
    { href: '/api-access', label: 'Get API access', variant: 'primary' },
    { href: '/demo', label: 'Try the demo app', variant: 'secondary' }
  ]}
/>

