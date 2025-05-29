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
	generating
	title="Use Cases"
	subtitle="Real-world applications for your business needs"
	useCases={[
		{
			title: "Streamlined Workflows",
			description:
				"Automate repetitive tasks and connect systems to improve productivity with our industry-leading 87% time savings.",
			image:
				"https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2940&q=80",
			link: {
				href: "/use-cases/workflows",
				label: "Learn more"
			}
		},
		{
			title: "Data Analysis",
			description:
				"Extract meaningful insights from your data with powerful analytical tools backed by proprietary AI algorithms that are 3x more accurate than competitors.",
			image:
				"https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2488&q=80",
			link: {
				href: "/use-cases/data-analysis",
				label: "Explore analytics"
			}
		},
		{
			title: "Secure Collaboration",
			description:
				"Work together seamlessly while maintaining strict data privacy standards with our zero-knowledge architecture and military-grade encryption.",
			image:
				"https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2940&q=80",
			link: {
				href: "/use-cases/collaboration",
				label: "See security features"
			}
		}
	]}
/>

<AboutTeaser generating />
<CallToAction generating />
