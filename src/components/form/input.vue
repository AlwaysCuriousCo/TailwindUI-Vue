<script>
import BaseComponent from 'primevue/basecomponent';

export default {
	name: 'InputText',
	extends: BaseComponent,
	emits: ['update:modelValue'],
	props: {
		modelValue: null
	},
	methods: {
		onInput(event) {
			this.$emit('update:modelValue', event.target.value);
		}
	},
	computed: {
		filled() {
			return this.modelValue != null && this.modelValue.toString().length > 0;
		}
	}
};
</script>

<template>
  <div>
	<label for="email" class="block text-sm font-medium leading-6 text-gray-900">Email</label>
	<div class="mt-2">
		<input :class="['p-inputtext p-component', { 'p-filled': filled }]" :value="modelValue" @input="onInput" v-bind="ptm('root')" />

	  <input type="email" name="email" id="email" class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" placeholder="you@example.com" />
	</div>
  </div>
</template>

<style scoped>

</style>
