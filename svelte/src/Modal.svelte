<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  const closeModal = () => dispatch("closemodal");
</script>

<style>
  .back {
    position: fixed;
    width: 100%;
    height: 100vh;
    background: rgba(0, 0, 0, 0.8);
    top: 0;
    left: 0;
    z-index: 10;
  }

  .modal {
    padding: 1rem;
    position: fixed;
    top: 10vh;
    left: 10%;
    width: 80%;
    max-height: 80vh;
    background: white;
    border-radius: 5px;
    z-index: 100;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.25);
    overflow: auto;
  }

  header {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2rem;
  }

  .content {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  footer {
    margin-bottom: -0.8rem;
    justify-content: flex-end;
    display: flex;
  }

  footer button {
    cursor: pointer;
  }
</style>

<div class="back" on:click={closeModal} />
<div class="modal">
  <header>
    <slot name="header">TEST</slot>
  </header>
  <div class="content">
    <slot />
  </div>
  <footer>
    <slot name="footer">
      <button on:click={closeModal}>Close</button>
    </slot>
  </footer>
</div>
