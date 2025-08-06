<svelte:options customElement={{ tag: "hello-world", shadow: "none" }} />

<script lang="ts">
  interface Props {
    name: string
  }
  let { name = $bindable("World") }: Props = $props()

  let counter = $state(0)
</script>

<h1>Hello {name}!</h1>

<label>
  Update your name
  <input bind:value={name} />
</label>

<br /><br />

<button
  onclick={() => {
    counter++
  }}>Click me</button
>

<h1>You have clicked the button {counter} times!</h1>
