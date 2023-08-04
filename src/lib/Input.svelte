<script>
  export let value = "";
  export let disabled = false;
  export let error = false;
  export let helperText = value;
  export let icon = "";
  export let iconPosition = "";
  export let size = "";
  export let fullwidth = "";
  export let multiline = false;
  export let rows = 1;
  export let labelID;

  const positionIcon = () => {
    if (icon !== "" && iconPosition === "start") {
      return "start";
    }

    if (icon !== "" && iconPosition === "end") {
      return "end";
    }
    return "";
  };
</script>

<label for={labelID} class={fullwidth}>
  {#if multiline !== true}
    <input
      class={` input ${error ? "error" : ""} ${disabled ? "disabled" : ""} ${
        helperText === value ? "" : "error"
      } ${iconPosition === "start" ? "padding" : ""} ${size} ${fullwidth}`}
      name={labelID}
      id={labelID}
      placeholder="Placeholder"
      {disabled}
      bind:value
      pattern="^[a-zA-Z0-9]+$"
    />
    <span class={positionIcon()}>{icon}</span>
  {:else}
    <label for={labelID} />
    <textarea
      name={labelID}
      id={labelID}
      cols="30"
      {rows}
      placeholder="Placeholder"
    />
  {/if}
</label>

<style>
  label {
    position: relative;
    display: block;
    width: fit-content;
  }

  textarea,
  .input {
    display: block;
    padding: 1rem 1.5rem;
    font-size: 1.1em;
    border: none;
    outline: none;
    border-radius: 7px;
    background-color: var(--input-bg);
  }
  textarea:hover,
  .input:hover {
    outline: currentColor solid 1px;
  }
  textarea:focus,
  .input:focus {
    outline: blueviolet solid 1px;
  }

  .error {
    outline: red solid 1px;
  }

  .error:hover {
    outline: currentColor solid 1px;
  }

  .error:focus {
    outline: red solid 1px;
  }

  .disabled {
    outline: none;
  }

  .disabled:hover {
    outline: none;
  }

  .disabled:focus {
    outline: none;
  }

  span.start {
    position: absolute;
    inset: 0.5rem auto 0.5rem 7px;
    font-size: 1.5em;
  }

  span.end {
    position: absolute;
    inset: 0.5rem 7px 0.5rem auto;
    font-size: 1.5em;
  }

  .padding {
    padding: 1rem 1rem 1rem 2.5rem;
  }

  .sm {
    padding: 0.5rem 1.5rem;
  }

  .md {
    padding: 1.5rem;
  }

  .fullwidth {
    min-width: 100%;
    width: 100%;
  }

  textarea {
    resize: none;
  }
</style>
