<script>
  import Button from "../shared/Button.svelte";
  import { fetchStudentData } from "../../services/service";

  let id;
  const submitHandler = () => {
    if (id) {
      fetchStudentData(id);
      id = "";
    }
  };
</script>

<style>
  .id-form {
    width: 100%;
    max-width: 800px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  form {
    /* width: 320px; */
    width: 100%;
    margin: 0 auto;
    text-align: center;
  }
  input {
    /* width: 100%;
    height: 50px;
    border-radius: 24px;
    box-shadow: 0px 2px 3px lightgray; */
    width: 90%;
    height: 100%;
    border-radius: 0px 24px 24px 0px;
    border: 0px;
    border-left: 1px solid lightgray;
  }
  .search-button {
    width: 15%;
    height: 100%;
    border-radius: 24px 0px 0px 24px;
    /* background-color: #ff4000; */
    /* color: white; */
    background-color: transparent;
    font-size: 20px;
    cursor: pointer;
    border: none;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .form-field {
    margin: 16px auto;
    width: 100%;
    height: 50px;
    border-radius: 24px;
    box-shadow: 0px 4px 4px lightgray;
    display: flex;
  }
</style>

<div class="id-form">

  <form on:submit|preventDefault={submitHandler}>
    <div class="form-field">
      <button class="search-button"><img src="search.svg" alt="Search" width="20" /></button>
      <input
      type="text"
      placeholder="학번"
      id="id"
      on:enter={submitHandler}
      bind:value={id} />
    </div>
    <!-- <Button>조회하기</Button> -->
  </form>

</div>
