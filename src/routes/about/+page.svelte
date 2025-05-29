<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
  {
    title: "Beneficence",
    description: "We aim to advance human well-being with every product and decision."
  },
  {
    title: "Empathy",
    description: "We build technology that listens, understands, and responds with genuine emotional intelligence."
  },
  {
    title: "Scientific legitimacy",
    description: "Our models are founded on rigorous, peer-reviewed research and real-world evidence."
  },
  {
    title: "Emotional primacy",
    description: "We place human feeling and experience at the center of every AI interaction."
  },
  {
    title: "Inclusivity",
    description: "We strive to serve, represent, and benefit people of every background and identity."
  },
  {
    title: "Transparency",
    description: "We communicate clearly, share our assumptions, and show how our technology works."
  },
  {
    title: "Consent",
    description: "We respect individual autonomy and secure explicit, meaningful consent in every use."
  }
];
</script>

<SecondaryHero
	title="AI that understands how you feel"
	subtitle="Grounded in science to build technology that supports human well-being"
	imageSrc="/generated/image-a-candid-scene-in-a-modern-nyc-office-wh.webp"
/>

<!-- Story Section -->
<Story
	paragraphs={[
		"Hume AI was founded on a simple idea: AI should help us feel understood. For too long, technology has struggled to respond to what makes us most human—emotion. Conversations with machines often feel lifeless or frustrating, driven by rules instead of real understanding. We saw a deep gap in how AI communicates and knew there had to be a better way—one that centers emotional intelligence, empathy, and well-being from the start.",
		"We began as a research lab focused on understanding how people express emotion in voice and behavior. That work quickly turned into technology—like EVI, the first voice interface that detects emotion and sounds like it truly cares, and Octave, which brings humanlike rhythm and emotional nuance to AI speech. Today, developers and leaders across health, education, robotics, and media are using our tools to bring natural, expressive interactions to the services people rely on every day.",
		"Our mission is to make AI more human—not just in tone, but in purpose. We're guided by an ethical framework that puts people first: empathy, transparency, consent, and real scientific rigor. This isn’t just about better tech—it’s about creating systems built to support human well-being. We believe AI should make people feel heard, not managed. That’s the future we’re building toward—one conversation at a time."
	]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
	stakeholderType="team"
	title="Our team."
	subtitle="Meet the people behind Hume AI."
	stakeholders={[
		{
			name: "Moses Oh",
			position: "Senior Research Engineer",
			bio: "I get to solve problems no one imagined five years ago and experience technologies no one will be able to live without in five years.",
			image: "/generated/image-a-professional-headshot-of-a-korean-amer.webp"
		}
	]}
/>




<!-- CTA Section -->
<CallToAction
  title="Build with emotional intelligence"
  subtitle="Join Hume AI’s mission—or bring empathic AI to yours"
  description="Help shape technology that supports human well-being. Explore our APIs or reach out to collaborate, research, or bring more empathy to your products."
  imageSrc="/generated/image-a-diverse-group-of-cheerful-researchers-.webp"
  callsToAction={[
    { href: '/get-access', label: 'Request API access', variant: 'primary' },
    { href: '/contact', label: 'Contact our team', variant: 'secondary' }
  ]}
/>
