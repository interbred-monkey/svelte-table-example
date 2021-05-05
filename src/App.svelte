<script lang="typescript">
  import ChildTable from './components/child-table/child-table.svelte';
  import Select from './components/select/select.svelte';
  import TableComponent from './components/expandable-table/expandable-table.svelte';
  const tableData = '';
  const resolver = console.log;
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>This is a table</h1>
  <hr />
  <Select />
  <widget1>
    <TableComponent>
      <div slot="childTable">
        <ChildTable />
      </div>
    </TableComponent>
  </widget1>
  <hr />
  <widget2>
    <TableComponent data={tableData}>
      <ChildTable {resolver} />
    </TableComponent>
  </widget2>
</main>

<hr />
