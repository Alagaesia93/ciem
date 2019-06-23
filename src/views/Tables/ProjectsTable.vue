<template>
  <div class="card shadow"
       :class="type === 'dark' ? 'bg-default': ''">
    <div class="card-header border-0"
         :class="type === 'dark' ? 'bg-transparent': ''">
      <div class="row align-items-center">
        <div class="col">
          <h3 class="mb-0" :class="type === 'dark' ? 'text-white': ''">
            {{title}}
          </h3>
        </div>
        <!-- <div class="col text-right">
          <base-button type="primary" size="sm">See all</base-button>
        </div> -->
      </div>
    </div>

    <div class="table-responsive">
      <base-table class="table align-items-center table-flush"
                  :class="type === 'dark' ? 'table-dark': ''"
                  :thead-classes="type === 'dark' ? 'thead-dark': 'thead-light'"
                  tbody-classes="list"
                  :data="tableData">
        <template slot="columns">
          <th>Cliente</th>
          <th>Stato</th>
          <th># Files</th>
          <th></th>
        </template>

        <template slot-scope="{row}">
          <th scope="row">
            <div class="media align-items-center">
              <a href="#" class="avatar rounded-circle mr-3">
                <img alt="Image placeholder" :src="row.img">
              </a>
              <div class="media-body">
                <span class="name mb-0 text-sm">{{row.title}}</span>
              </div>
            </div>
          </th>
          <td>
            <badge class="badge-dot mr-4" :type="row.statusType">
              <i :class="`bg-${row.statusType}`"></i>
              <span class="status">{{row.status}}</span>
            </badge>
          </td>
          <td>
            {{ row.num_files }}
          </td>
          <td>
            <router-link to="/profile">
              <div class="col text-right">
                <base-button type="primary" size="sm">Visualizza</base-button>
              </div>
            </router-link>
          </td>
        </template>

      </base-table>
    </div>

    <div class="card-footer d-flex justify-content-end"
         :class="type === 'dark' ? 'bg-transparent': ''">
      <base-pagination total="30"></base-pagination>
    </div>

  </div>
</template>
<script>
  export default {
    name: 'projects-table',
    props: {
      type: {
        type: String
      },
      title: String
    },
    data() {
      return {
        tableData: [
          {
            img: 'img/theme/bootstrap.jpg',
            title: 'Cliente 1',
            status: 'pending',
            statusType: 'warning',
            num_files: 200
          },
          {
            img: 'img/theme/angular.jpg',
            title: 'Cliente 2',
            budget: '$1800 USD',
            status: 'completed',
            statusType: 'success',
            completion: 100,
            num_files: 12
          },
          {
            img: 'img/theme/sketch.jpg',
            title: 'Cliente 3',
            budget: '$3150 USD',
            status: 'delayed',
            statusType: 'danger',
            completion: 72,
            num_files: 8
          },
          {
            img: 'img/theme/react.jpg',
            title: 'Cliente 4',
            budget: '$4400 USD',
            status: 'on schedule',
            statusType: 'info',
            completion: 90,
            num_files: 400
          },
          {
            img: 'img/theme/vue.jpg',
            title: 'Cliente 5',
            budget: '$2200 USD',
            status: 'completed',
            statusType: 'success',
            completion: 100,
            num_files: 167
          }
        ]
      }
    }
  }
</script>
<style>
</style>
