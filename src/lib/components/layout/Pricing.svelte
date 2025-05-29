<!--
@component Pricing

Please update features according to the company's product offering. Do not remove this comment.
-->
<script lang="ts">
	// Types
	type PricingTier = {
		name: string;
		monthlyPrice?: number | null;
		yearlyPrice?: number | null;
		description: string;
		features: string[];
		cta: {
			label: string;
			href: string;
		};
		highlight?: boolean;
	};

	type PricingFeature = {
		name: string;
		tiers: {
			[key: string]: boolean | string;
		};
	};

	// Components
	import Button from "$lib/components/ui/Button.svelte";
	import SectionHeader from "./SectionHeader.svelte";
	import IconCheck from "~icons/lucide/check";
	import IconX from "~icons/lucide/x";
	import NumberFlow from "@number-flow/svelte";
	import LogoScroller from "./LogoScroller.svelte";

	// Props
	const {
		title = "Pricing built for every stage",
		subtitle = "From early experiments to enterprise-scale applications, choose the plan that supports your growth. All plans include access to Hume AI’s emotional intelligence APIs with pricing and support that scale with you.",
		tierNames = ["Developer", "Business", "Enterprise"],
		features = [
			{
				name: "Monthly included usage",
				tiers: {
					Developer: "1,000 credits",
					Business: "50,000+ credits",
					Enterprise: "Custom volume"
				}
			},
			{
				name: "API access (EVI 3, Octave, Expression, Custom Models)",
				tiers: {
					Developer: true,
					Business: true,
					Enterprise: true
				}
			},
			{
				name: "Additional usage (pay-as-you-go)",
				tiers: {
					Developer: true,
					Business: "Discounted",
					Enterprise: "Volume rates"
				}
			},
			{
				name: "Latency",
				tiers: {
					Developer: "Standard",
					Business: "Standard + Instant mode",
					Enterprise: "Custom"
				}
			},
			{
				name: "Voice customization",
				tiers: {
					Developer: "Basic prompts",
					Business: "Advanced prosody control",
					Enterprise: "Custom voice profiles"
				}
			},
			{
				name: "Analytics dashboard",
				tiers: {
					Developer: false,
					Business: true,
					Enterprise: "Custom reports"
				}
			},
			{
				name: "Flexible LLM integration",
				tiers: {
					Developer: "Built-in",
					Business: "Built-in & external",
					Enterprise: "Custom system"
				}
			},
			{
				name: "Phone deployment support",
				tiers: {
					Developer: false,
					Business: true,
					Enterprise: true
				}
			},
			{
				name: "Support",
				tiers: {
					Developer: "Community & email",
					Business: "Priority email",
					Enterprise: "Dedicated manager"
				}
			},
			{
				name: "SLA",
				tiers: {
					Developer: false,
					Business: "Optional add-on",
					Enterprise: "Guaranteed 99.9%"
				}
			},
			{
				name: "Security & compliance",
				tiers: {
					Developer: "Standard",
					Business: "Standard",
					Enterprise: "Enterprise-grade"
				}
			},
			{
				name: "Custom integrations",
				tiers: {
					Developer: false,
					Business: false,
					Enterprise: true
				}
			},
			{
				name: "Onboarding & training",
				tiers: {
					Developer: "Docs/guides",
					Business: "Email onboarding",
					Enterprise: "Personalized/training"
				}
			}
		],
		tiers = [
			{
				name: "Developer",
				monthlyPrice: 0,
				yearlyPrice: 0,
				description: "For developers and researchers starting out. Get 1,000 credits/month free and access all APIs. No credit card required.",
				features: [
					"1,000 credits/month included",
					"API access to EVI 3, Octave, Expression Measurement, Custom Models",
					"Standard latency",
					"Basic voice customization via prompt",
					"Community and email support",
					"No SLA or analytics"
				],
				cta: {
					label: "Start free",
					href: "/signup?plan=developer"
				}
			},
			{
				name: "Business",
				monthlyPrice: 99,
				yearlyPrice: 79, // Discounted with annual
				description: "For startups, creators, and growing teams building for production. All APIs, faster modes, analytics, and priority support.",
				features: [
					"50,000+ credits/month included",
					"Faster instant mode options",
					"Advanced voice controls",
					"Analytics dashboard",
					"Flexible LLM integration",
					"Phone deployment",
					"Priority email support"
				],
				cta: {
					label: "View pricing",
					href: "/signup?plan=business"
				},
				highlight: true
			},
			{
				name: "Enterprise",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "For organizations requiring custom terms, scale, and security. Custom usage, compliance, integrations, and white glove onboarding.",
				features: [
					"Custom high-volume usage",
					"Dedicated manager",
					"Guaranteed SLA",
					"Enterprise-grade compliance",
					"Custom integrations & analytics",
					"Personalized onboarding & training"
				],
				cta: {
					label: "Contact sales",
					href: "/contact"
				}
			}
		]
	}: {
		title?: string;
		subtitle?: string;
		tiers?: PricingTier[];
		features?: PricingFeature[];
		tierNames?: string[];
		caption?: string;
	} = $props();

	// State
	let annual = $state(true);
</script>

<section class="section-py section-px container mx-auto">
	<div class="flex flex-col items-baseline justify-between lg:flex-row">
		<SectionHeader {title} {subtitle} />

		<div class="mb-8 flex justify-center">
			<div class="inline-flex items-center rounded-full bg-gray-100 p-0.5 dark:bg-gray-800">
				<Button
					variant="ghost"
					size="sm"
					class=" {!annual ? 'bg-white shadow-sm dark:bg-gray-700' : ''}"
					onclick={() => (annual = false)}
				>
					Monthly
				</Button>
				<Button
					variant="ghost"
					size="sm"
					rounded
					class={annual ? "bg-white shadow-sm dark:bg-gray-700" : ""}
					onclick={() => (annual = true)}
				>
					Annual <span class="text-primary-600 dark:text-primary-400 text-footnote">Save 20%</span>
				</Button>
			</div>
		</div>
	</div>

	<div class="bb grid gap-6 md:grid-cols-2 lg:grid-cols-3">
		{#each tiers as tier}
			<div
				class="flex flex-col rounded-xl bg-white p-6 ring ring-gray-200 transition-all duration-300 dark:bg-gray-800 dark:ring-gray-700"
				class:ring-2={tier.highlight}
				class:ring-primary={tier.highlight}
				class:dark:ring-primary-700={tier.highlight}
				class:translate-y-[-4px]={tier.highlight}
			>
				<div class="mb-8">
					<h3 class="text-title3 mb-4 dark:text-white">{tier.name}</h3>
					<div class="mt-2 flex items-baseline">
						{#if tier.monthlyPrice === null && tier.yearlyPrice === null}
							<span class="text-title2 dark:text-white">Custom</span>
						{:else}
							<NumberFlow
								class="text-title2 [&::part\(suffix\)]:text-caption dark:text-white"
								format={{
									style: "currency",
									currency: "USD",
									trailingZeroDisplay: "stripIfInteger"
								}}
								value={annual ? tier.yearlyPrice : tier.monthlyPrice}
								suffix="/month"
							/>
						{/if}
					</div>
					<p class="text-callout text-emphasis-medium mt-3 dark:text-gray-300">
						{tier.description}
					</p>
				</div>

				<div class="mb-8 flex-grow">
					<ul class="space-y-3">
						{#each tier.features as feature}
							<li class="flex items-center gap-2">
								<IconCheck class="text-primary-600 dark:text-primary-400 size-5 flex-shrink-0" />
								<span class="text-body text-emphasis-medium dark:text-gray-300">{feature}</span>
							</li>
						{/each}
					</ul>
				</div>

				<div class="mt-auto">
					<Button
						href={tier.cta.href}
						variant={tier.highlight ? "primary" : "secondary"}
						class="w-full"
					>
						{tier.cta.label}
					</Button>
				</div>
			</div>
		{/each}
	</div>
	<div class="mt-32">
		<!-- Responsive table wrapper with horizontal scroll on mobile -->
		<!-- <div class=" hidden overflow-x-auto px-4 sm:mx-0 sm:block sm:px-0">
			<table
				class="w-full min-w-full border-separate border-spacing-0 border-gray-200 text-left dark:border-gray-700"
			>
				<thead>
					<tr>
						<th
							class="sticky left-0 min-w-[120px] border-b border-gray-200 bg-white dark:border-gray-700 dark:bg-gray-900"
						>
							<span class="sr-only">Feature</span>
						</th>
						{#each tierNames as tierName}
							<th
								class="text-headline min-w-[100px] border-b border-gray-200 p-4 text-start font-normal dark:border-gray-700"
							>
								{tierName}
							</th>
						{/each}
					</tr>
				</thead>
				<tbody>
					{#each features as feature}
						<tr>
							<td class="text-caption">
								{feature.name}
							</td>
							{#each tierNames as tierName}
								<td
									class="min-w-[100px] border-b border-gray-200 p-4 text-start text-gray-600 dark:border-gray-700 dark:text-gray-300"
								>
									{#if typeof feature.tiers[tierName] === "boolean"}
										{#if feature.tiers[tierName]}
											<IconCheck
												class="text-primary-600 dark:text-primary-400 mx-auto size-5 sm:mx-0"
											/>
										{:else}
											<IconX class="mx-auto size-5 text-gray-400 sm:mx-0" />
										{/if}
									{:else}
										{feature.tiers[tierName]}
									{/if}
								</td>
							{/each}
						</tr>
					{/each}
				</tbody>
			</table>
		</div> -->

		<!-- Mobile feature comparison (alternative view for very small screens) -->
		<div>
			<!-- Universal pricing comparison for mobile -->
			<div class="overflow-x-auto">
				<table class="w-full border-collapse">
					<!-- Sticky header with tier names -->
					<thead class="border-border sticky top-0 z-10 border-b">
						<tr>
							<th class="min-w-[120px] py-3 text-left">
								<span class="sr-only">Feature</span>
							</th>
							{#each tierNames as tierName, i}
								<th class="text-caption min-w-[100px] py-3 text-left dark:text-white">
									{tierName}
								</th>
							{/each}
						</tr>
					</thead>
					<tbody class="divide-border divide-y">
						{#each features as feature}
							<tr>
								<td class="text-body py-3 pr-8 font-medium lg:pr-0 dark:text-white">
									{feature.name}
								</td>
								{#each tierNames as tierName, i}
									<td class="py-3">
										{#if typeof feature.tiers[tierName] === "boolean"}
											{#if feature.tiers[tierName]}
												<IconCheck class="text-primary-900 dark:text-primary-400 size-5" />
											{:else}
												<IconX class="size-5 text-gray-400" />
											{/if}
										{:else}
											<span class="text-callout font-medium text-gray-700 dark:text-gray-300">
												{feature.tiers[tierName]}
											</span>
										{/if}
									</td>
								{/each}
							</tr>
						{/each}
					</tbody>
				</table>
			</div>
		</div>
	</div>
	<LogoScroller />
</section>

<style lang="postcss">
	@reference '../../../app.css';

	:global(number-flow-svelte)::part(suffix) {
		@apply text-sm text-gray-400 dark:text-gray-500;
	}
</style>
