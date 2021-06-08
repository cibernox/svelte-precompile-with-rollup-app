<script>
  import { addMessages, init, getLocaleFromNavigator /*, register */ } from 'svelte-intl-precompile';
  import en from '../locales/en.js';
  // @ts-ignore
  addMessages('en', en);
  // register('es', () => import('../../locales/en.js')); <-- use this approach if you want locales to be load lazily

  init({
    fallbackLocale: 'en',
    initialLocale: getLocaleFromNavigator()
  });
	import { t } from 'svelte-intl-precompile'	
	export let name;
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<p>{$t('basic')}</p>
	<p>{$t('interpolated', { values: { val: name } })}</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>