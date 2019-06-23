<template>
    <div class="my-5 py-5">
        <div class="container-fluid">
            <div class="row">
                <div class="col-xl-4 order-xl-2 mb-5 mb-xl-0">
                    <div class="card card-profile shadow">
                        <div class="row justify-content-center">
                            <div class="col-lg-3 order-lg-2">
                                <div class="card-profile-image">
                                  <img src="img/theme/team-4-800x800.jpg" class="rounded-circle">
                                </div>
                            </div>
                        </div>
                        <div class="card-header text-center border-0 pt-8 pt-md-4 pb-0 pb-md-4">
                            <!-- <div class="d-flex justify-content-between">
                                <base-button size="sm" type="info" class="mr-4">Connect</base-button>
                                <base-button size="sm" type="default" class="float-right">Message</base-button>
                            </div> -->
                        </div>
                        <div class="card-body pt-0 pt-md-4">
                            <div class="row">
                                <div class="col">
                                    <div class="card-profile-stats d-flex justify-content-center mt-md-5">
                                        <div>
                                          <span class="heading">Pending</span>
                                          <span class="description">In attesa di appuntamento</span>
                                        </div>
                                        <div>
                                            <span class="heading">8</span>
                                            <span class="description">Appuntamenti</span>
                                        </div>
                                        <div>
                                            <span class="heading">3</span>
                                            <span class="description">Files</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="text-center">
                                <h3>
                                    Jessica Jones<span class="font-weight-light">, 27</span>
                                </h3>
                                <div class="h5 font-weight-300">
                                    <i class="ni location_pin mr-2"></i>Bucharest, Romania
                                </div>
                                <div class="h5 mt-4">
                                    <i class="ni business_briefcase-24 mr-2"></i>Azienda X
                                </div>
                                <div>
                                    <i class="ni education_hat mr-2"></i>Genova
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="col-xl-8 order-xl-1">
                    <card shadow type="secondary">
                        <div slot="header" class="bg-white border-0">
                            <div class="row align-items-center">
                                <div class="col-8">
                                    <h3 class="mb-0">File condivisi</h3>
                                </div>
                                <div class="col-4 text-right">
                                  <a href="#!" id="select-files" class="btn btn-sm btn-primary">Carica nuovo</a>
                                </div>
                            </div>
                        </div>
                        <template>
                          <div class="card-group">
                            <div class="card">
                              <img src="img/theme/team-1-800x800.jpg" class="card-img-top" alt="...">
                              <div class="card-body">
                                <h5 class="card-title">Visura.pdf</h5>
                                <p class="card-text"><i>Come da accordi allego documento richiesto</i></p>
                                <p class="card-text"><small class="text-muted">Caricato 3 ore fa</small></p>
                              </div>
                            </div>
                            <div class="card">
                              <img src="img/theme/team-2-800x800.jpg" class="card-img-top" alt="...">
                              <div class="card-body">
                                <h5 class="card-title">Contratto.pdf</h5>
                                <p class="card-text">File contratto.pdf</p>
                                <p class="card-text"><small class="text-muted">Caricato 22 giorni fa</small></p>
                              </div>
                            </div>
                            <div class="card">
                              <img src="img/theme/team-3-800x800.jpg" class="card-img-top" alt="...">
                              <div class="card-body">
                                <h5 class="card-title">Stato lavori</h5>
                                <p class="card-text"><i>Come da contratto in allegato lo stato lavorit</i></p>
                                <p class="card-text"><small class="text-muted">Caricato 1 mese fa</small></p>
                              </div>
                            </div>
                          </div>
                        </template>
                    </card>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
  export default {
    name: 'user-profile',
    data() {
      return {
        model: {
          username: '',
          email: '',
          firstName: '',
          lastName: '',
          address: '',
          city: '',
          country: '',
          zipCode: '',
          about: '',
        }
      }
    },
    mounted() {
      const Uppy = require('@uppy/core')
      const Dashboard = require('@uppy/dashboard')
      require('@uppy/core/dist/style.css')
      require('@uppy/dashboard/dist/style.css')
      Uppy().use(Dashboard, {
        trigger: '#select-files'
      })

      // uppy.on('complete', result => {
      //   // console.log('Upload complete! We’ve uploaded these files:', result.successful)
      // })
    }
  };
</script>
<style></style>
