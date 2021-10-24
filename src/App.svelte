<script lang="ts">
import MyComponent from './lib/components/MyComponent.svelte'
const MyOtherComponent = import('./lib/components/MyOtherComponent.svelte')
</script>

<MyComponent/>
{#await MyOtherComponent} <!-- wait for it to load --->
  Other component is loading...
{:then MyOtherComponent}
  <MyOtherComponent.default/>
{/await}