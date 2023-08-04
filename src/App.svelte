<script>
  import Input from "./lib/Input.svelte";
  let newValue = "text";
  let multiline = true;
  let fullwidth = "fullwidth";
</script>

<main>
  <h1>Inputs components with Svelte</h1>

  <div class="input_container">
    <code>{`<Input />`}</code>
    <Input labelID="labelID1" />
  </div>

  <div class="input_container">
    <code>{`<Input error />`}</code>
    <Input labelID="labelID2" error={true} />
  </div>

  <div class="input_container">
    <code>{`<Input disabled />`}</code>
    <Input labelID="labelID3" disabled={true} />
  </div>

  <div class="input_container">
    <code>{`<Input helperText = "correct text" />`}</code>
    <Input labelID="labelID4" helperText="correct text" />
  </div>

  <div class="input_container">
    <code>{`<Input icon = "☎️" iconPosition="start" />`}</code>
    <Input labelID="labelID5" icon="☎️" iconPosition="start" />
  </div>

  <div class="input_container">
    <code>{`<Input icon="🔒" iconPosition="end"  />`}</code>
    <Input labelID="labelID6" icon="🔒" iconPosition="end" />
  </div>

  <div class="input_container">
    <code>{`<Input value = "text" />`}</code>
    <Input labelID="labelID7" bind:value={newValue} />
  </div>

  <div class="input_container">
    <code>{`<Input size="sm" />`}</code>
    <Input labelID="labelID8" size="sm" />
  </div>

  <div class="input_container">
    <code>{`<Input size="md" />`}</code>
    <Input labelID="labelID9" size="md" />
  </div>

  <div class="input_container">
    <code>{`<Input fullwidth />`}</code>
    <Input labelID="labelID10" {fullwidth} />
  </div>

  <div class="input_container">
    <code>{`<Input multiline rows={4} />`}</code>
    <Input labelID="labelID11" {multiline} rows={4} />
  </div>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
  }

  .input_container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    width: 100%;
  }

  h1 {
    text-align: center;
  }
</style>
