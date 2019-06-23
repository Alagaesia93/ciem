<template>
  <div class="mt-5">
    <div class="container-fluid">
      <div class="row">
        <div class="col">
          <projects-table type="dark" title="Clienti"></projects-table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ProjectsTable from './Tables/ProjectsTable'

export default {
  name: 'tables',
  components: {
    ProjectsTable
  }
}
</script>

