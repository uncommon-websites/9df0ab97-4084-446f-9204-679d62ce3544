<script lang="ts">
	// Components
	import UseCases from "$lib/components/layout/UseCases.svelte";
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import Hero from "$lib/components/layout/hero-sections/Hero.svelte";
</script>

<Hero
	title="Elevate your business with thoughtful design"
	subtitle="Solutions that enhance user experience, and improve visual communication."
	imageSrc="/sample.png"
	generating
/>
<LogoScroller label="" generating />

<Summary
	title="What we do"
	text="Hume AI builds empathic AI models and tools that understand and respond to human emotion. We help people and organizations create more human-centered products with emotional intelligence, always optimizing for well-being."
/>

<Testimonials
	testimonials={[
		{
			name: "Marta Bouchard",
			position: "Product Manager",
			company: "ForesightQ",
			quote:
				"Rolling out Hume AI cut our onboarding from a full week to just one day. That meant we shipped updates a lot faster—saving precious dev time and budget before launch.",
			image:
				"/generated/image-a-female-product-manager-smiling-in-a-co.webp"
		},
		{
			name: "Tariq Jensen",
			position: "Senior Engineer",
			company: "Waveform Robotics",
			quote:
				"We used the emotion API to spot edge-case frustration in user calls early. That let us patch a risky bug and avoid a costly rollback. Hume saved us real money and downtime.",
			image:
				"/generated/image-a-male-engineer-with-a-beard-working-in-.webp"
		},
		{
			name: "Selene Dao",
			position: "Research Scientist",
			company: "Caledon University",
			quote:
				"Manual annotation for emotion analysis would have eaten half our grant. With Hume, we finished data labeling in weeks for a fraction of the cost—and with higher accuracy.",
			image:
				"/generated/image-a-female-scientist-in-a-bustling-univers.webp"
		}
	]}
/>

<Features
	title="Emotionally intelligent by design"
	subtitle="AI technology that listens, understands, and responds with empathy."
	features={[
		{
			title: "Empathic voice interface",
			description: "Engage users with real-time speech and natural emotional expression—no voice cloning needed."
		},
		{
			title: "Multimodal emotion measurement",
			description: "Detect over two dozen emotions across audio, text, and facial cues for true contextual understanding."
		},
		{
			title: "LLM-powered, deeply customizable",
			description: "Change voice, style, and emotional tone with a prompt—bring your own LLM or use ours."
		},
		{
			title: "Proprietary research and data",
			description: "Built on science—over 1 million participants and 40+ peer-reviewed studies power every model."
		},
		{
			title: "Robust API for developers",
			description: "Low-latency, usage-based APIs make emotion AI easy to integrate and scale."
		},
		{
			title: "Ethics at the core",
			description: "Every model is guided by globally recognized values—beneficence, empathy, and scientific legitimacy."
		}
	]}
/>

<UseCases
	title="Use Cases"
	subtitle="Real-world applications for your business needs"
	useCases={[
		{
			title: "Emotionally aware health support",
			description: "AI that senses and responds to the emotional state of patients, improving support in telehealth, eldercare, and preventative wellness programs.",
			image: "/generated/image-a-health-professional-attentively-provid.webp",
			link: {
				href: "/use-cases/emotionally-aware-health-support",
				label: "See health applications"
			}
		},
		{
			title: "Human-centered customer experiences",
			description: "Voice AI that adapts to callers’ emotional tone—reducing churn, preventing escalation, and making every interaction more personal.",
			image: "/generated/image-a-diverse-team-of-call-center-agents-eng.webp",
			link: {
				href: "/use-cases/human-centered-customer-experiences",
				label: "See customer use"
			}
		},
		{
			title: "Expressive content creation",
			description: "Creators generate rich, emotionally nuanced audio and voices for podcasts, audiobooks, and video with simple instructions—no studio required.",
			image: "/generated/image-a-creative-individual-passionately-recor.webp",
			link: {
				href: "/use-cases/expressive-content-creation",
				label: "See creator tools"
			}
		}
	]}
/>

<AboutTeaser />
<CallToAction
  title="AI that understands how you feel"
  subtitle="Bring emotional intelligence to your product, voice, or research"
  description="Help your users feel heard. Build more human connections with empathic voice and expression AI—trusted by developers, creators, and researchers everywhere."
  imageSrc="/generated/image-a-cheerful-businesswoman-dressed-in-prof.webp"
  callsToAction={[
    {
      href: "/get-started",
      label: "Start building",
      variant: "primary"
    },
    {
      href: "/contact",
      label: "Contact sales",
      variant: "secondary"
    }
  ]}
/>
