<script>
    import Layout from '../components/Layout.svelte';
    import { Table, TableBody, TableBodyCell, TableBodyRow, TableHead, TableHeadCell, Toggle, Button } from 'flowbite-svelte';
</script>

<Layout>
    <div>
        <div class="flex items-center justify-between mb-4">
            <h1 class="mb-4">Grupos</h1>
            <Button>
                Crear grupo
            </Button>
        </div>
        <Table>
          <TableHead>
            <TableHeadCell>ID</TableHeadCell>
            <TableHeadCell>Nombre Grupo</TableHeadCell>
            <TableHeadCell>Descripción</TableHeadCell>
            <TableHeadCell>Correos</TableHeadCell>
            <TableHeadCell>Acciones</TableHeadCell>

          </TableHead>
          <TableBody class="divide-y">
            <TableBodyRow>
              <TableBodyCell>1</TableBodyCell>
              <TableBodyCell>Grupo 01</TableBodyCell>
              <TableBodyCell>Grupo de prueba</TableBodyCell>
              <TableBodyCell>
                <div>
                    <h3>mijel.dev@gmail.com</h3>
                    <h3>juan@gmail.com</h3>
                </div>
              </TableBodyCell>
              <TableBodyCell>
                <Toggle checked={true}>Activo</Toggle>
              </TableBodyCell>
            </TableBodyRow>
            <TableBodyRow>
                <TableBodyCell>2</TableBodyCell>
                <TableBodyCell>Grupo 02</TableBodyCell>
                <TableBodyCell>Grupo de prueba</TableBodyCell>
                <TableBodyCell>
                  <div>
                      <h3>mijel.dev@gmail.com</h3>
                      <h3>juan@gmail.com</h3>
                  </div>
                </TableBodyCell>
                <TableBodyCell>
                    <Toggle checked={true}>Activo</Toggle>
                  </TableBodyCell>
              </TableBodyRow>
          </TableBody>
        </Table>
    </div>
</Layout>    