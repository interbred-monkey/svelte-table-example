<script lang="typescript">
  export let data = '';

  const tableState = {};

  // async get data
  const tableData = [{
    id: 'id1',
    name: 'name1',
    description: 'description1'
  },{
    id: 'id2',
    name: 'name2',
    description: 'description1'
  },{
    id: 'id3',
    name: 'name3',
    description: 'description1'
  },{
    id: 'id4',
    name: 'name4',
    description: 'description1'
  }]

  const tableHeaders = Object.keys(tableData[0]);

  const showTable = (id) => {
    if (!tableState[id]) {
      tableState[id] = {expanded: false}
    }
    tableState[id].expanded = !tableState[id].expanded;
  }
</script>

<style>
  table, td, th {
    border: 1px solid;
  }
</style>

<table>
  <tr>
    <th></th>
    {#each tableHeaders as header}
    <th>{header}</th>
    {/each}
  </tr>
  {#each tableData as {id, name, description}}
  <tr on:click={() =>showTable(id)}>
    <td>></td>
    <td>{id}</td>
    <td>{name}</td>
    <td>{description}</td>
  </tr>
  { #if tableState[id] && tableState[id].expanded }
  <tr><td colspan="4"><slot name="childTable">No data to show</slot></td></tr>
  { /if }
  {/each}
</table>
