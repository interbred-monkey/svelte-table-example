<script lang="typescript">
  import Select, { Option } from '@smui/select';

  let fruits = ['Apple', 'Orange', 'Banana', 'Mango'];
  let fruitChoice = '';
</script>

<Select
  enhanced
  bind:value={fruitChoice}
  label="Enhanced Input"
  class="demo-select-width"
  menu$class="demo-select-width">
  <Option value="" />
  {#each fruits as fruit}
    <Option value={fruit} selected={fruitChoice === fruit}>{fruit}</Option>
  {/each}
</Select>
