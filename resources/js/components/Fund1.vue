<template>
<div class="container-fluid">
        <!-- Info boxes -->
        <div class="row">
          <div class="col-12 col-sm-6 col-md-3">
            <div class="info-box">
              <span class="info-box-icon bg-info elevation-1"><i class="fa fa-chart-bar"></i></span>

              <div class="info-box-content">
                <span class="info-box-text">FTSE Index</span>
                <span class="info-box-number">
                  {{TopBarInfo[1]}}
                  <!-- <small></small> -->
                </span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
          </div>
          <!-- /.col -->
          <div class="col-12 col-sm-6 col-md-3">
            <div class="info-box mb-3">
              <span class="info-box-icon bg-danger elevation-1"><i class="fa fa-chart-pie"></i></span>

              <div class="info-box-content">
                <span class="info-box-text">Actual Stock Value </span>
                <span class="info-box-number">{{TopBarInfo[2]}}</span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
          </div>
          <!-- /.col -->

          <!-- fix for small devices only -->
          <div class="clearfix hidden-md-up"></div>

          <div class="col-12 col-sm-6 col-md-3">
            <div class="info-box mb-3">
              <span class="info-box-icon bg-success elevation-1"><i class="fa fa-chart-area"></i></span>

              <div class="info-box-content">
                <span class="info-box-text">FTSE Index</span>
                <span class="info-box-number" >{{TopBarInfo[3]}}% <i class="fas fa-arrow-up green" ></i></span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
          </div>
          <!-- /.col -->
          <div class="col-12 col-sm-6 col-md-3">
            <div class="info-box mb-3">
              <span class="info-box-icon bg-warning elevation-1"><i class="fas fa-chart-line"></i></span>

              <div class="info-box-content">
                <span class="info-box-text">Portfolio Rating</span>
                <span class="info-box-number">{{TopBarInfo[4]}}%<i class="fas fa-arrow-down red"></i>  </span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
          </div>
          <!-- /.col -->
        </div>
        <!-- /.row -->

        <div class="row">
          <div class="col-md-7">
            <div class="card">
                
                
                <div class="card-header">
                   <h5 class="card-title">Your Investments</h5>
                </div>
                <div class="card-body">
                   <div class="row">
                    <div class="col-md-12">
                      <!--<img src="img/graphs.png" class="card-img-top">-->
                      <!-- <div class="small">
                           <line-chart :chart-data="datacollection"></line-chart>
                           <button @click="fillData()">Randomize</button> 
                            </div> -->
                      <!-- <highcharts :constructor-type="'stockChart'" :options="chartOptions"></highcharts> -->
                        <!-- <canvas id="mix2" count="1"></canvas> -->
                        
                        <chartjs-line :datalabel="'Barclays'" :backgroundcolor="'rgba(136, 226, 27,0.4)'"  :bordercolor="'rgb(136, 226, 27)'" target="mix2" :data="this.Barclaysplot"  :bind="true"  :linetension="0"  :labels="['11-Mar-2019','12-Mar-2019','13-Mar-2019','14-Mar-2019','15-Mar-2019', '16-Mar-2019']" :height="800" ></chartjs-line>
                        
                    </div>
                  </div>
                </div>
            </div>
            <!-- /.card -->
 
          
          </div>
          <!-- /.col -->

           <div class="col-md-5">
            <div class="card">
              <div class="card-header">
                <h5 class="card-title">Fund 1 (Barclays)</h5>

               
              </div>
              <!-- /.card-header -->
              <div class="card-body">
                <div class="row">
                  <div class="col-md-12">
                    <p style="text-align:justify">
                      {{DashboardInfo}}
                    </p>
                   
                  </div>
                  <!-- /.col -->

                </div>
                <!-- /.row -->
              </div>
              <!-- ./card-body -->
  
            </div>
            <!-- /.card -->
          </div>
          <!-- /.col -->
        </div>
        <!-- /.row -->

        <!-- Main row -->
        <div class="row">
          <!-- Left col -->
          <div class="col-md-8">
           
            
            
           
            
            
            <!-- /.row -->

        
          </div>
          <!-- /.col -->

          <div class="col-md-4">
            <!-- Info Boxes Style 2 -->
            
            <!-- /.info-box -->
            
            <!-- /.info-box -->
           
            <!-- /.info-box -->
            
            <!-- /.info-box -->
             <!-- /.info-box -->
         

          
          </div>
          <!-- /.col -->
        </div>
        <!-- /.row -->
      </div>
</template>


<script>
//   import {Chart} from 'highcharts-vue'
//   import Highcharts from 'highcharts'
// import stockInit from 'highcharts/modules/stock'
// stockInit(Highcharts)
import {Line} from 'vue-chartjs'
    export default {
            extends: Line,

            data(){
              return{
                barclaysNews:{},
                microFocusNews:{},
                SSENews:{},
                VodafoneNews:{},
                DashboardInfo:{},
                DashboardInfo2:{},
                TopBarInfo:{},
                Barclaysplot:[],
                 
                // chartOptions: {
                //   series: [{
                //     data: [1,2,3] // sample data
                //   }]
                // }
                
              }
            },
            // components: {
            //  highcharts: Chart
            // },
            methods:{
            
           loadDashboardInfo(){
             this.loadDashInfo();  
             this.loadTopBarInfo();  
             this.loadGraphInfo();     

          },
              loadGraphInfo(){
                  
                 this.loadBarcPlot();
                 
                 
               },loadBarcPlot(){
                                  //console.log ("BarclaysNEWs"); 
                const instance = axios.create({
                headers: {
                  
                          'Content-Type' : "application/x-www-form-urlencoded; charset=UTF-8",
                          // 'Access-Control-Allow-Origin' : "*",
                          // 'Access-Control-Allow-Headers': 'Origin, X-Requested-With, Content-Type, Accept',
                          // 'Access-Control-Allow-Methods': 'GET, POST, PATCH, PUT, DELETE, OPTIONS'
                          
                        
                },
                });

              delete instance.defaults.headers.common['X-CSRF-TOKEN'];
              delete instance.defaults.headers.common['X-Requested-With'];

              //https://cors-escape.herokuapp.com/https://maximum.blog/@shalvah/posts

                instance.get('https://flask-way.herokuapp.com/getBarclays')
              //instance.get('https://cors-escape.herokuapp.com/http://flask-way.herokuapp.com')
                .then(response => {
                //   var FIRS,firstStep,respondents;
                // firstStep = JSON.stringify(response.data.ArriaText)
                // respondents = JSON.parse(firstStep);
                // FIRS = JSON.parse(respondents)
                // console.log(FIRS);
              //this.DashboardInfo = respondents;
              
              var c = JSON.stringify(response.data.Barclay[0])
              var a = JSON.parse(c);
              var d = JSON.parse(a)
              //var b = a;
              //var b = a.replace(/(<([^>]+)>)/ig,"");
             // var e = b.replace("&nbsp;f","f");
             var  divisor = 10
             for(var i = 0, length = d.length; i < length; i++){
                  d[i] /= divisor;  // `a[i].x /= d` is shorthand for `a[i].x = a[i].x / d`
                  //d[i] /= divisor;
              }
              var zb = d;
              //var zb = d.splice(83,180)
              //var z =d.splice(169,180)
              this.Barclaysplot = zb;
              //var par_2 = e.slice(375)
              //this.DashboardInfo = e.slice(0,385);
              //this.DashboardInfo2 = e.slice(385);

              //var f = e.slice(0,385)
              
              //console.log(this.Barclaysplot)
            });

               }, 
               
               loadTopBarInfo(){
              //console.log ("BarclaysNEWs"); 
                  const instance = axios.create({
                  headers: {
                    
                            'Content-Type' : "application/x-www-form-urlencoded; charset=UTF-8",
                             
                          
                  },
                  });

                delete instance.defaults.headers.common['X-CSRF-TOKEN'];
                delete instance.defaults.headers.common['X-Requested-With'];

                //https://cors-escape.herokuapp.com/https://maximum.blog/@shalvah/posts

                instance.get('https://moneyarc.herokuapp.com/')
                
                  .then(response => {
                  
                var c = JSON.stringify(response.data.raw_data.ID_updown)
                var a = JSON.parse(c);

                var ftseDat = JSON.stringify(response.data.raw_data.ftse)
              
                var actualData = JSON.stringify(response.data.raw_data.acc_value)
                var del_index = JSON.stringify(response.data.raw_data.del_index)
                var del_pf = JSON.stringify(response.data.raw_data.del_pf)
                // var b = a;
                // var b = a.replace(/(<([^>]+)>)/ig,"");
                // var e = b.replace("&nbsp;f","f");
                //this.DashboardInfo = e;
                //var par_2 = e.slice(375)
                var TopArr = [a,ftseDat,actualData,del_index,del_pf]
                this.TopBarInfo = TopArr 

              });

          },
          loadDashInfo(){
              //console.log ("BarclaysNEWs"); 
                const instance = axios.create({
                headers: {
                  
                          'Content-Type' : "application/x-www-form-urlencoded; charset=UTF-8",
                          // 'Access-Control-Allow-Origin' : "*",
                          // 'Access-Control-Allow-Headers': 'Origin, X-Requested-With, Content-Type, Accept',
                          // 'Access-Control-Allow-Methods': 'GET, POST, PATCH, PUT, DELETE, OPTIONS'
                          
                        
                },
                });

              delete instance.defaults.headers.common['X-CSRF-TOKEN'];
              delete instance.defaults.headers.common['X-Requested-With'];

              //https://cors-escape.herokuapp.com/https://maximum.blog/@shalvah/posts

                instance.get('https://moneyarc.herokuapp.com/')
              //instance.get('https://cors-escape.herokuapp.com/http://flask-way.herokuapp.com')
                .then(response => {
                //   var FIRS,firstStep,respondents;
                // firstStep = JSON.stringify(response.data.ArriaText)
                // respondents = JSON.parse(firstStep);
                // FIRS = JSON.parse(respondents)
                // console.log(FIRS);
              //this.DashboardInfo = respondents;
              
              var c = JSON.stringify(response.data.ArriaText[1])
              var a = JSON.parse(c);
              var b = a;
              var b = a.replace(/(<([^>]+)>)/ig,"");
              var e = b.replace("&nbsp;f","f");
              this.DashboardInfo = e;
              // //var par_2 = e.slice(375)
              // this.DashboardInfo = e.slice(0,375);
              // this.DashboardInfo2 = e.slice(375);

              //var f = e.slice(0,375)
              
              //console.log(f)
            });
          },


        },
        
        mounted() {
            console.log('Component mounted.')
            this.loadDashboardInfo();
            
            //this.renderChart(this.datacollection, this.options);
            
        },
        
    }
</script>



