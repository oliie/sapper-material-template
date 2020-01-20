<script>
  import Button, { Label, Icon, Group } from "@smui/button";
  import Checkbox from "@smui/checkbox";
  import FormField from "@smui/form-field";
  import Slider from "@smui/slider";

  let clicked = 0;
  let selected = false;
  let value = 0;
</script>

<style lang="scss">
  .grayed {
    opacity: 0.6;
  }

  * {
    font-family: Roboto !important;
  }

  h1 {
    color: #99c6ba;
  }

  h2 {
    color: #cbe0c0;
  }

  p {
    border-bottom: 1px solid #99c6ba;
    padding-bottom: 1rem;
  }

  code {
    font-size: 0.8rem;
    color: #99c6ba;
    font-family: Roboto Mono !important;
  }
</style>

<div class="container">
  <h1>Welcome!</h1>
  <h2>This is a template with Material Design</h2>

  <p>
    Overrides to the SCSS can be done in
    <code>theme/_smui-theme.scss.</code>
    <br />
    Feel free do remove
    <code>Example.svelte</code>
    and start building a wonderful application!
  </p>

  <div>
    <Button variant="outlined" on:click={() => clicked++}>
      <Icon class="material-icons">thumb_up</Icon>
      <Label>Click Me</Label>
    </Button>

    <Group>
      <Button color="secondary" variant="raised" on:click={() => clicked++}>
        One
      </Button>

      <Button variant="raised" on:click={() => clicked++}>Two</Button>

      <Button color="secondary" variant="raised" on:click={() => clicked++}>
        Three
      </Button>
    </Group>

    <Button variant="raised" color="secondary">Click Me</Button>

    <Button ripple={false} variant="raised">Click Me</Button>

    <Button dense={true} variant="unelevated">Click Me</Button>

    <p class="mdc-typography--body1">
      {#if clicked}
        You've clicked the button {clicked} time{clicked === 1 ? '' : 's'}.
      {:else}
        <span class="grayed">You haven't clicked the button.</span>
      {/if}
    </p>
  </div>

  <div>
    <FormField>
      <Checkbox bind:checked={selected} />
      <span slot="label">Check me.</span>
    </FormField>
  </div>

  <div>
    <Slider discrete displayMarkers min={-10} max={10} step={1} bind:value />
  </div>
</div>
