<script>
  import "./app.css";
  import AddToDo from "./AddToDo.svelte";

  let toDos = [
    { data: { title: "Go to..."}, ref: { value: { id: "1" } } },
    { data: { title: "Breakfast"} }
  ];
  async function handelClick(ref) {
    toDos = toDos.filter(todo => todo.ref !== ref);
  }
</script>

<main>
  <h1>To-Do List</h1>
  <div class="">
    <AddToDo bind:toDos={toDos}/>
    <div class="">
      <h3>Today's list:</h3>
      <ul>
        {#each toDos as toDo}
          <li>
              <label>
                <div class="checkbox"> 
                  <input type="checkbox" name="packersOff" value="1"> 
                  <label class="strikethrough">{toDo?.data?.title}</label> 
                </div>
                <button class="remove-button" on:click={() => handelClick(toDo.ref)}>remove</button>
                <hr>
              </label>
              
            
          </li>
        {/each}
      </ul>
    </div>
  </div>
</main>

<!--maiza radhiya marjjonzzzzzzzzzzzzzzz-->