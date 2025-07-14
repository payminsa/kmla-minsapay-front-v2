<script>
  import Header from "./components/layouts/Header.svelte";
  import Footer from "./components/layouts/Footer.svelte";

  import Tabs from "./components/shared/Tabs.svelte";

  import Booth from "./components/booth/Booth.svelte";
  import Student from "./components/student/Student.svelte";

  // tabs
  let items = ["학생 메뉴", "부스 메뉴"];
  let activeItem = "학생 메뉴";
  const tabChangeHandler = event => (activeItem = event.detail);
</script>

<style>
  main {
    text-align: center;
    /* padding: 3em; */
    margin: 0 auto;
    max-width: none;
  }
  .container {
    margin: 2em;
    padding: 0 20%;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-height: 300px;
  }
  .main {
    display: flex;
    flex-direction: column;
    min-height: 100%;
  }
  .flex-container-header {
    display: flex;
    /* flex-direction: column; */
    align-items: center;
    justify-content: space-between;
    /* border-bottom: 1px solid #ccc; */
    padding: 0px 16px;
  }
  @media screen and (max-width: 640px) {
    main {
      padding: 1em;
    }
    .flex-container-header {
      flex-direction: column;
      align-items: center;
      border-bottom: 1px solid #ccc;
    }
    .container {
      padding: 0;
      margin: 2em 0;
    }
  }
</style>

<main class="main">
  <div class="flex-container-header">
    <Header />
    <Tabs {items} {activeItem} on:tabChange={tabChangeHandler} />
  </div>
  <div class="container">
    {#if activeItem === '학생 메뉴'}
      <Student />
    {:else if activeItem === '부스 메뉴'}
      <Booth />
    {/if}
  </div>

  <Footer />
</main>
