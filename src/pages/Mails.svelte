<script>
  import { onMount } from 'svelte';
    import Layout from '../components/Layout.svelte';
    import { Table, TableBody, TableBodyCell, TableBodyRow, TableHead, TableHeadCell, Toggle, Button, Modal, Label, Input } from 'flowbite-svelte';
    let data = [];
    let defaultModal = false;
    let name = '';
    let number = '';
    let email = '';
    let active = true;

    let urlAPI = import.meta.env.VITE_API_URL

    const getData = async () => {
      try {
        const response = await fetch(urlAPI + '/correos');
        const result = await response.json();
        data = result[0]; // Asigna los datos de la API a la variable data
      } catch (error) {
        console.error('Error al obtener datos de la API:', error);
      }
    }

    const enviarFormulario = async () => {
      try {
        const response = await fetch(urlAPI + '/correos', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({ name, number, email, active })
        });

        console.log(response)
        getData()

      } catch (error) {
        console.error('Error en la solicitud:', error);
      }
    };


    onMount(() => {
      getData()
    })
</script>

<Layout>
  <Modal title="Terms of Service" bind:open={defaultModal} autoclose>
    <form on:submit|preventDefault={enviarFormulario}>
      <!-- <label>
        Nombre:
        <input type="text" bind:value={name} />
      </label> -->

      <div class="mb-6">
        <Label for="name" class="block mb-2">Nombre</Label>
        <Input id="name" size="lg" placeholder="Nombre..." bind:value={name} />
      </div>

      <div class="mb-6">
        <Label for="number" class="block mb-2">Número</Label>
        <Input id="number" size="lg" placeholder="999999999..." bind:value={number} />
      </div>

      <div class="mb-6">
        <Label for="email" class="block mb-2">Email</Label>
        <Input id="email" size="lg" type="email" placeholder="example@example.com" bind:value={email} />
      </div>

      <div class="mb-6">
        <Label for="active" class="block mb-2">Estado</Label>
        <Toggle id="active" bind:checked={active}>Activado</Toggle>
      </div>
      </form>
    <svelte:fragment slot="footer">
      <Button on:click={() => enviarFormulario()}>Crear</Button>
      <Button color="alternative">Cancelar</Button>
    </svelte:fragment>
  </Modal>
    <div>
        <div class="flex items-center justify-between mb-4">
            <h1 class="mb-4">Emails</h1>
            <Button on:click={() => (defaultModal = true)}>
                Agregar
            </Button>
        </div>
        <Table>
          <TableHead>
            <TableHeadCell>ID</TableHeadCell>
            <TableHeadCell>Nombre</TableHeadCell>
            <TableHeadCell>Email</TableHeadCell>
            <TableHeadCell>Acciones</TableHeadCell>
          </TableHead>
          <TableBody class="divide-y">
            {#each data as item (item.id)}
              <TableBodyRow key={item.id}>
                <TableBodyCell>{item.id}</TableBodyCell>
                <TableBodyCell>{item.name}</TableBodyCell>
                <TableBodyCell>{item.email}</TableBodyCell>
                <TableBodyCell>
                  <Toggle checked={item.active}>Activo</Toggle>
                </TableBodyCell>
              </TableBodyRow>
            {/each}
          </TableBody>
        </Table>
    </div>
</Layout>    
