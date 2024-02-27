<script>
  import { Router, links, Route } from "svelte-routing";
  import About from "./pages/About.svelte";
  import Home from "./pages/Home.svelte";
  import Layout from "./components/Layout.svelte";
  import Mails from "./pages/Mails.svelte";
  import Groups from "./pages/Groups.svelte";
  import EmailsToSend from "./pages/EmailsToSend.svelte";
</script>

<main>
  <Router>
    <div>
      <Route path="/" component={Home} />
      <Route path="/correos" component={Mails} />
      <Route path="/grupos" component={Groups} />
      <Route path="/envio" component={EmailsToSend} />
    </div>
  </Router>
</main>

<style>
</style>
