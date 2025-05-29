<script lang="ts">
	// Types

	// Components
	import SectionHeader from "$lib/components/layout/SectionHeader.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Card from "$lib/components/ui/Card.svelte";
	import JobList, { type JobOpening } from "./JobList.svelte";

	// Icons
	import IconBriefcase from "~icons/lucide/briefcase";
	import IconUsers from "~icons/lucide/users";
	import IconHeart from "~icons/lucide/heart";
	import IconGlobe from "~icons/lucide/globe";

	// Constants
	const SECTION_BASE_CLASSES = "section-py section-px container mx-auto";
	const GRADIENT_BG_CLASSES =
		"bg-gradient-to-br from-gray-50 to-gray-100 dark:from-gray-900 dark:to-gray-800";
	const ICON_CONTAINER_CLASSES =
		"bg-primary-50 text-primary-600 dark:bg-primary-950 dark:text-primary-400 flex items-center justify-center rounded-full";

	const benefits = [
  {
    title: "Be a pioneer",
    description:
      "Shape the next wave of empathic AI—work at the intersection of research and application.",
    icon: IconBriefcase
  },
  {
    title: "Ownership and growth",
    description:
      "Take the lead on meaningful projects, publish research, and unlock new career chapters.",
    icon: IconUsers
  },
  {
    title: "Support & flexibility",
    description:
      "Equity, competitive pay, medical/dental/vision, unlimited PTO, hybrid NYC and Bay Area offices, and remote options.",
    icon: IconHeart
  }
];

	const openings: JobOpening[] = [
		// Engineering
		{
			title: "Senior Frontend Developer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Backend Engineer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Design Engineer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Design
		{
			title: "UX/UI Designer",
			department: "Design",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Product Designer",
			department: "Design",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Product
		{
			title: "Product Manager",
			department: "Product",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Product Analyst",
			department: "Product",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Marketing
		{
			title: "Marketing Specialist",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Content Strategist",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Social Media Manager",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		}
	];

	const employeeTestimonials = [
  {
    name: "Sasha Aurin",
    position: "Software Engineer",
    company: "API Team",
    quote:
      "I’ve never worked somewhere with this level of openness and collaboration, across research and engineering. Everyone has a voice, and it genuinely shapes how we build empathic AI.",
    image: "/generated/image-a-professional-headshot-of-a-young-white.webp"
  },
  {
    name: "Jordi Vega",
    position: "Senior Product Manager",
    company: "Voice Interfaces",
    quote:
      "Hume invests in your growth. I joined as a data analyst, but I’ve built product-wide impact areas and now mentor others. It’s a rare place where initiative turns into opportunity.",
    image: "/generated/image-a-professional-headshot-of-a-middle-aged.webp"
  },
  {
    name: "Minji El-Masri",
    position: "Research Ops Lead",
    company: "Research Operations",
    quote:
      "The work is challenging in the best way—but what makes it sustainable is the trust. I’ve always felt empowered to prioritize health, experiment freely, and ask for support. People genuinely want you to thrive.",
    image: "/generated/image-a-professional-headshot-of-an-east-asian.webp"
  }
];

	const processSteps = [
  {
    step: 1,
    title: "Apply online",
    description:
      "Send us your resume and a short note about what excites you about Hume AI."
  },
  {
    step: 2,
    title: "Screening call",
    description:
      "30-minute virtual chat to get to know you, your experience, and your ambitions."
  },
  {
    step: 3,
    title: "Role assessment",
    description:
      "Take-home project, technical or functional interview—tailored to your field."
  },
  {
    step: 4,
    title: "Meet the team",
    description:
      "Conversations with future teammates and leadership. Mutual fit is important!"
  },
  {
    step: 5,
    title: "Offer & onboarding",
    description:
      "Receive your offer and get support through a smooth onboarding into our unique culture."
  }
];

	const values = [
  {
    icon: IconHeart,
    title: "Impact is personal",
    description:
      "We center well-being and empathy in both our products and our culture."
  },
  {
    icon: IconUsers,
    title: "Science meets shipping",
    description:
      "We blend research rigor with a bias for building and iteration."
  },
  {
    icon: IconGlobe,
    title: "Kind, candid collaboration",
    description:
      "Ideas matter more than titles. We communicate openly, care for each other, and build together."
  }
];
</script>

<!-- Hero Section -->

<SecondaryHero
  title="Design AI for human well-being"
  subtitle="Grow with a team that leads with empathy"
  imageSrc="/generated/image-a-diverse-team-of-professionals-engaged-.webp"
/>

<!-- Why Join Us Section -->
<section class={SECTION_BASE_CLASSES}>
	<SectionHeader title="Why join us?" subtitle="Build your career while making an impact" />

	<div class="mt-16 grid gap-4 md:grid-cols-3">
		{#each benefits as benefit}
			<Card {...benefit} />
		{/each}
	</div>
</section>

<!-- Culture Section -->
<Culture {values} />

<Testimonials testimonials={employeeTestimonials} />

<!-- Application Process -->
<section class={SECTION_BASE_CLASSES}>
	<div class="mx-auto">
		<h2 class="text-title1 mb-16">Our application process</h2>

		<div class="grid gap-12 md:grid-cols-3">
			{#each processSteps as { step, title, description }, i}
				<div class="flex flex-col">
					<div class="{ICON_CONTAINER_CLASSES} mb-6 size-11">
						<span class="text-headline">{step}</span>
					</div>
					<h3 class="text-headline mb-3">{title}</h3>
					<p class="text-body text-emphasis-low">{description}</p>
				</div>
			{/each}
		</div>
	</div>
</section>
<!-- Current Openings Section -->
<section class={GRADIENT_BG_CLASSES}>
	<div class="section-px section-py container mx-auto grid w-full items-start lg:grid-cols-2">
		<SectionHeader title="Current openings" subtitle="Find your perfect role" />

		<JobList {openings} />
	</div>
</section>
