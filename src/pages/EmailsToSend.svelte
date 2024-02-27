<script>
  import Layout from '../components/Layout.svelte';
  import { Textarea, Button } from 'flowbite-svelte';
  import { Table, TableBody, TableBodyCell, TableBodyRow, TableHead, TableHeadCell, Checkbox } from 'flowbite-svelte';

  let textareaprops = {
    id: 'message',
    name: 'message',
    label: 'Your message',
    rows: 4,
    placeholder: 'Escribe el texto para tu correo...'
  };
</script>

<Layout>
  <h1 class="mb-5">Emails to send</h1>
  <div class="flex mb-5 w-full">
    <div class="w-2/4	pr-4">
      <Textarea {...textareaprops} />
    </div>
    <div class="w-2/4	pl-4">
      <Table hoverable={true}>
        <TableHead>
          <TableHeadCell class="!p-4">
            <Checkbox />
          </TableHeadCell>
          <TableHeadCell>ID</TableHeadCell>
          <TableHeadCell>Nombre</TableHeadCell>
          <TableHeadCell>Descripción</TableHeadCell>
          <TableHeadCell>Correos</TableHeadCell>
        </TableHead>
        <TableBody class="divide-y">
          <TableBodyRow>
            <TableBodyCell class="!p-4">
              <Checkbox />
            </TableBodyCell>
            <TableBodyCell>1</TableBodyCell>
            <TableBodyCell>Grupo 01</TableBodyCell>
            <TableBodyCell>Grupo de prueba</TableBodyCell>
            <TableBodyCell>
              <div>
                  <h3>mijel.dev@gmail.com</h3>
                  <h3>juan@gmail.com</h3>
              </div>
            </TableBodyCell>
          </TableBodyRow>
          <TableBodyRow>
            <TableBodyCell class="!p-4">
              <Checkbox />
            </TableBodyCell>
            <TableBodyCell>1</TableBodyCell>
            <TableBodyCell>Grupo 01</TableBodyCell>
            <TableBodyCell>Grupo de prueba</TableBodyCell>
            <TableBodyCell>
              <div>
                  <h3>mijel.dev@gmail.com</h3>
                  <h3>juan@gmail.com</h3>
              </div>
            </TableBodyCell>
          </TableBodyRow>
          <TableBodyRow>
            <TableBodyCell class="!p-4">
              <Checkbox />
            </TableBodyCell>
            <TableBodyCell>1</TableBodyCell>
            <TableBodyCell>Grupo 01</TableBodyCell>
            <TableBodyCell>Grupo de prueba</TableBodyCell>
            <TableBodyCell>
              <div>
                  <h3>mijel.dev@gmail.com</h3>
                  <h3>juan@gmail.com</h3>
              </div>
            </TableBodyCell>
          </TableBodyRow>
        </TableBody>
      </Table>
    </div>
  </div>
  <div class="flex justify-center">
    <Button>Enviar correo</Button>
  </div>
  
</Layout>    