<script>
  export let tableData = [{}]
  export let variant
  export let gap = 'md'
  export let borderColor
  export let fontColor
</script>

<div class="container-table" style="border-color: {borderColor}">
  <table class={variant} style="color: {fontColor}">
    <thead>
      <tr>
        {#each Object.keys(tableData[0]) as columnHeading}
          <th class={gap} style="border-color: {borderColor}; text-align: center;">{columnHeading.charAt(0).toUpperCase() + columnHeading.slice(1)}</th>
        {/each}
      <tr/>
    </thead>
    <tbody>
      {#each Object.values(tableData) as row}
        <tr class={`variant-${variant}`}>
          {#each Object.values(row) as cell}
            <td class={gap} style="border-color: {borderColor}; text-align: center;">{cell}</td>
          {/each}
        </tr>
      {/each}
    </tbody>
    <tfoot>
      <tr>
        {#each Object.keys(tableData[0]) as columnFooter}
          <th class={gap} style="text-align: center;">{columnFooter.charAt(0).toUpperCase() + columnFooter.slice(1)}</th>
        {/each}
      <tr/>
    </tfoot>
  </table>
</div>

<style>

.container-table {
  width: max-content;
  border: 1px solid #AAAAAA;
  border-radius: 10px;
  padding: 10px;
}

table {
  margin: auto;
  border-collapse: collapse;
  overflow: hidden;
}

 .simple tr td, .simple thead tr th {
  border-bottom: 1px solid #AAAAAA;
}

.variant-striped:nth-child(odd) {
  background: #285E61;
}

.sm {
  padding: 10px 20px 10px 20px;
}

.md {
  padding: 10px 40px 10px 40px;
}

.lg {
  padding: 10px 60px 10px 60px;
}

</style>