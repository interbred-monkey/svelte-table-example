<script lang="typescript">
  import ChildTable from './components/child-table/child-table.svelte';
  import TableComponent from './components/expandable-table/expandable-table.svelte';
  const tableData = '';
  const resolver = console.log;
</script>

<main>
  <h1>This is a table</h1>
  <hr>
  <widget1>
    <TableComponent>
      <div slot="childTable" >
        <ChildTable />
      </div>
    </TableComponent>
  </widget1>
  <hr>
  <widget2>
    <TableComponent data={tableData}>
      <ChildTable resolver={resolver}/>
    </TableComponent>
  </widget2>
</main>

<hr>
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
