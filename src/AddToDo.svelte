<script>

  let value = "";
  export let toDos;
  async function handleClick() {

    toDos.push({ data: { title: value }, ref: { value: { id: Math.random() } } });
    toDos = toDos;
    value = "";
  }

  import "./app.css";
</script>

<form class="todo-wrapper" on:submit|preventDefault={handleClick}>
  <div>
    <input class="input-list" required placeholder="Input new" bind:value={value}/>
  </div>
  <button class="submit-button" type="submit" >
    + Add
  </button>
</form>

<style lang="css">

</style>