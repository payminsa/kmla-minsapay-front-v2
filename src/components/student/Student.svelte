<script>
  import IDForm from "./IDForm.svelte";
  import PayHistoryList from "./PayHistoryList.svelte";
</script>

<style>
  .student-container {
    width: 100%;
    max-width: 800px;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 20px;
  }
  @media screen and (max-width: 640px) {
    .icon {
      display: none;
    }
  }
</style>

<div class="student-container">
  <img class="icon" src="/favicon.png" alt="Icon" width="100" height="100" />
  <IDForm />
  <PayHistoryList />
</div>
