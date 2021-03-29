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
                        <canvas id="mix2" count="5"></canvas>
                        <chartjs-line :datalabel="'FTSE'" :backgroundcolor="'rgba(255, 10, 27,0.4)'" :bordercolor="'rgb(255, 10, 27)'" target="mix2" :data="this.FTSEplot" :bind="true" :linetension="0" :labels="['11-Mar-2019','12-Mar-2019','13-Mar-2019','14-Mar-2019','15-Mar-2019', '16-Mar-2019']"  :height="800"  ></chartjs-line>
                        <chartjs-line :datalabel="'Barclays'" :backgroundcolor="'rgba(136, 226, 27,0.4)'"  :bordercolor="'rgb(136, 226, 27)'" target="mix2" :data="this.Barclaysplot"  :bind="true"  :linetension="0"  :labels="['11-Mar-2019','12-Mar-2019','13-Mar-2019','14-Mar-2019','15-Mar-2019', '16-Mar-2019']" :height="800" ></chartjs-line>
                        <chartjs-line :datalabel="'MicroFocus'" :backgroundcolor="'rgba(0, 83, 239,0.4)'"  :bordercolor="'rgb(0, 83, 239)'" target="mix2" :data="this.MicroFundsplot"  :bind="true" :linetension="0"   :labels="['11-Mar-2019','12-Mar-2019','13-Mar-2019','14-Mar-2019','15-Mar-2019', '16-Mar-2019']"  :height="800"  ></chartjs-line>
                        <chartjs-line :datalabel="'SSE'" :backgroundcolor="'rgba(246, 255, 0,0.4)'" :bordercolor="'rgb(246, 255, 0)'"  target="mix2" :data="this.SSEplot"    :linetension="0" :bind="true"  :labels="['11-Mar-2019','12-Mar-2019','13-Mar-2019','14-Mar-2019','15-Mar-2019', '16-Mar-2019']" :height="800"  ></chartjs-line>
                        <chartjs-line :datalabel="'Vodafone'" :backgroundcolor="'rgba(244, 66, 226,0.4)'" :bordercolor="'rgb(244, 66, 226)'" target="mix2" :data="this.Vodaplot"    :bind="true" :linetension="0"  :labels="['11-Mar-2019','12-Mar-2019','13-Mar-2019','14-Mar-2019','15-Mar-2019', '16-Mar-2019']" :height="800"  ></chartjs-line>
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
                <h5 class="card-title">Portfolio Summary</h5>

               
              </div>
              <!-- /.card-header -->
              <div class="card-body">
                <div class="row">
                  <div class="col-md-12">
                    <p style="text-align:justify">
                      {{DashboardInfo}}
                    </p>
                    <p style="text-align:justify">
                      {{DashboardInfo2}}
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
           
            <div class="row">
              <div class="col-md-12">
                <!-- DIRECT CHAT -->
                <div class="card direct-chat direct-chat-warning">
                  <div class="card-header">
                    <h3 class="card-title">Barclays plc</h3>

                    <div class="card-tools">
                      <button type="button" class="btn btn-tool" data-widget="collapse"><i class="fa fa-minus"></i>
                      </button>
                     
                      <button type="button" class="btn btn-tool" data-widget="remove"><i class="fa fa-times"></i>
                      </button>
                    </div>
                  </div>
                  <!-- /.card-header -->
                  <div class="card-body">
                    <!-- Conversations are loaded here -->
                    <div class="direct-chat-messages">
                      <!-- Message. Default to the left -->
                      <div class="direct-chat-msg">
                      
                        <!-- /.direct-chat-img -->
                        <div style="border-top:2px solid black; margin-bottom:5px" v-for="barclaysNewsItem in barclaysNews.articles" :key="barclaysNewsItem.articles">
                          <div><h4>{{barclaysNewsItem.title}}</h4></div>
                          <div> <b><small>{{barclaysNewsItem.publishedAt}}</small></b></div>
                          <div>{{barclaysNewsItem.content}}</div>
                          <a :href="barclaysNewsItem.url" class="card-link" target="_blank">Read more</a>
                          
                        </div>
                        <!-- /.direct-chat-text -->
                      </div>
                      <!-- /.direct-chat-msg -->

      
                    </div>
                    <!--/.direct-chat-messages-->

                    
                    <!-- /.direct-chat-pane -->
                  </div>
                  <!-- /.card-body -->
                  
                </div>
                <!--/.direct-chat -->
              </div>
            </div>  
            <div class="row">  
              <!-- /.col -->
              <div class="col-md-12">
                <!-- DIRECT CHAT -->
                <div class="card direct-chat direct-chat-warning">
                  <div class="card-header">
                    <h3 class="card-title"> Micro Focus Int'l plc</h3>

                    <div class="card-tools">
                      <button type="button" class="btn btn-tool" data-widget="collapse"><i class="fa fa-minus"></i>
                      </button>
                    
                      <button type="button" class="btn btn-tool" data-widget="remove"><i class="fa fa-times"></i>
                      </button>
                    </div>
                  </div>
                  <!-- /.card-header -->
                  <div class="card-body">
                    <!-- Conversations are loaded here -->
                    <div class="direct-chat-messages">
                      <!-- Message. Default to the left -->
                      <div class="direct-chat-msg">
                      
                        <!-- /.direct-chat-img -->
                        <div style="border-top:2px solid black; margin-bottom:5px" v-for="microFocusNewsItem in microFocusNews.articles" :key="microFocusNewsItem.articles">
                          <div><h4>{{microFocusNewsItem.title}}</h4></div>
                          <div> <b><small>{{microFocusNewsItem.publishedAt}}</small></b></div>
                          <div>{{microFocusNewsItem.content}}</div>
                          <a :href="microFocusNewsItem.url" class="card-link" target="_blank">Read more</a>
                          
                        </div>
                        <!-- /.direct-chat-text -->
                      </div>
                      <!-- /.direct-chat-msg -->

      
                    </div>
                    <!--/.direct-chat-messages-->

                    
                    <!-- /.direct-chat-pane -->
                  </div>
                  <!-- /.card-body -->
                  
                </div>
                <!--/.direct-chat -->
              </div>
              <!-- /.col -->

             
            </div>
            <!-- /.row -->
           
            <div class="row">
              <div class="col-md-12">
                <!-- DIRECT CHAT -->
                <div class="card direct-chat direct-chat-warning">
                  <div class="card-header">
                    <h3 class="card-title">SSE plc</h3>

                    <div class="card-tools">
                      <button type="button" class="btn btn-tool" data-widget="collapse"><i class="fa fa-minus"></i>
                      </button>
                     
                      <button type="button" class="btn btn-tool" data-widget="remove"><i class="fa fa-times"></i>
                      </button>
                    </div>
                  </div>
                  <!-- /.card-header -->
                  <div class="card-body">
                    <!-- Conversations are loaded here -->
                    <div class="direct-chat-messages">
                      <!-- Message. Default to the left -->
                      <div class="direct-chat-msg">
                      
                        <!-- /.direct-chat-img -->
                        <div style="border-top:2px solid black; margin-bottom:5px" v-for="SSENewsItem in SSENews.articles" :key="SSENewsItem.articles">
                          <div><h4>{{SSENewsItem.title}}</h4></div>
                          <div> <b><small>{{SSENewsItem.publishedAt}}</small></b></div>
                          <div>{{SSENewsItem.content}}</div>
                          <a :href="SSENewsItem.url" class="card-link" target="_blank">Read more</a>
                          
                        </div>
                        <!-- /.direct-chat-text -->
                      </div>
                      <!-- /.direct-chat-msg -->

      
                    </div>
                    <!--/.direct-chat-messages-->

                    </div>
                    <!-- /.direct-chat-pane -->
                  </div>
                <!--/.direct-chat -->
              </div>
              <!-- /.col -->
            </div>
            <div class="row">
              <div class="col-md-12">
                <!-- DIRECT CHAT -->
                <div class="card direct-chat direct-chat-warning">
                  <div class="card-header">
                    <h3 class="card-title"> Vodafone Group plc</h3>

                    <div class="card-tools">
                      <button type="button" class="btn btn-tool" data-widget="collapse"><i class="fa fa-minus"></i>
                      </button>

                      <button type="button" class="btn btn-tool" data-widget="remove"><i class="fa fa-times"></i>
                      </button>
                    </div>
                  </div>
                  <!-- /.card-header -->
                   <div class="card-body">
                    <!-- Conversations are loaded here -->
                    <div class="direct-chat-messages">
                      <!-- Message. Default to the left -->
                      <div class="direct-chat-msg">
                      
                        <!-- /.direct-chat-img -->
                        <div style="border-top:2px solid black; margin-bottom:5px" v-for="VodafoneNewsItem in VodafoneNews.articles" :key="VodafoneNewsItem.articles">
                          <div><h4>{{VodafoneNewsItem.title}}</h4></div>
                          <div> <b><small>{{VodafoneNews.publishedAt}}</small></b></div>
                          <div>{{VodafoneNews.content}}</div>
                          <a :href="VodafoneNews.url" class="card-link" target="_blank">Read more</a>
                          
                        </div>
                        <!-- /.direct-chat-text -->
                      </div>
                      <!-- /.direct-chat-msg -->

      
                    </div>
                    <!--/.direct-chat-messages-->

                    
                    <!-- /.direct-chat-pane -->
                  </div>
                  <!-- /.card-body -->
                 
                </div>
                <!--/.direct-chat -->
              </div>
              <!-- /.col -->

           
            </div>
            <!-- /.row -->

        
          </div>
          <!-- /.col -->

          <div class="col-md-4">
            <!-- Info Boxes Style 2 -->
            <div class="info-box mb-3 bg-warning">
              <span class="info-box-icon"><img src="img/barclays.png"/></span>
              
              <div class="info-box-content">
                <span class="info-box-text">Barclays plc</span>
                <span class="info-box-number" v-if="barclaysNews.articles && barclaysNews.articles.length > 1">{{barclaysNews.articles.length}} News Articles</span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
            <div class="info-box mb-3 bg-success">
              <span class="info-box-icon"><img src="img/microFocustransparent.png"/></span>

              <div class="info-box-content">
                <span class="info-box-text">Micro Focus Int'l plc</span>
                <span class="info-box-number" v-if="microFocusNews.articles &&  microFocusNews.articles.length > 1">{{microFocusNews.articles.length}} News Articles</span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
            <div class="info-box mb-3 bg-danger">
              <span class="info-box-icon"><img src="img/sse.png"/></span>

              <div class="info-box-content">
                <span class="info-box-text">SSE plc</span>
                <span class="info-box-number" v-if="SSENews.articles && SSENews.articles.length > 1">{{SSENews.articles.length}} News Articles</span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
            <div class="info-box mb-3 bg-info">
              <span class="info-box-icon"><img src="img/vodafone.png"/></span>

              <div class="info-box-content">
                <span class="info-box-text">Vodafone Group plc</span>
                <span class="info-box-number" v-if="VodafoneNews.articles && VodafoneNews.articles.length > 1">{{VodafoneNews.articles.length}} News Articles</span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
             <!-- /.info-box -->
            <div class="info-box mb-3 bg-success">
              <span class="info-box-icon"><i class="fas fa-newspaper"></i></span>

              <div class="info-box-content">
                <span class="info-box-text">NEWSSOURCE:NewsAPI</span>
                <span class="info-box-number">https://newsapi.org/</span>
              </div>
              <!-- /.info-box-content -->
            </div>

          
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
    export default {
          
            data(){
              return{
                barclaysNews:{},
                microFocusNews:{},
                SSENews:{},
                VodafoneNews:{},
                DashboardInfo:{},
                DashboardInfo2:{},
                TopBarInfo:{},
                FTSEplot:[],
                Barclaysplot:[],
                MicroFundsplot:[],
                SSEplot:[],
                Vodaplot:[],

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
                  //              loadMicroPlot();
                  // loadSSEPlot();
                  // loadVodaPlot(); 

          },
               loadGraphInfo(){
                  this.loadFTSEPlot();
                 this.loadBarcPlot();
                 this.loadMicroPlot();
                  this.loadSSEPlot();
                  this.loadVodaPlot();
               },
              loadFTSEPlot(){
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

                instance.get('https://flask-way.herokuapp.com/getFTSE')
              //instance.get('https://cors-escape.herokuapp.com/http://flask-way.herokuapp.com')
                .then(response => {
                //   var FIRS,firstStep,respondents;
                // firstStep = JSON.stringify(response.data.ArriaText)
                // respondents = JSON.parse(firstStep);
                // FIRS = JSON.parse(respondents)
                // console.log(FIRS);
              //this.DashboardInfo = respondents;
              
              var c = JSON.stringify(response.data.FTSE[0])
              var a = JSON.parse(c);
              var d = JSON.parse(a)
              //var b = a;
              //var b = a.replace(/(<([^>]+)>)/ig,"");
             // var e = b.replace("&nbsp;f","f");
             var  divisor = 100
             for(var i = 0, length = d.length; i < length; i++){
                  d[i] /= divisor;  // `a[i].x /= d` is shorthand for `a[i].x = a[i].x / d`
                 // d[i] /= divisor;
                 d[i] -= 50;
              }
              var za = d;
              //var za = d.splice(83,180)
              //var z = d.splice(83,124)
              this.FTSEplot = za;
              //var par_2 = e.slice(375)
              //this.DashboardInfo = e.slice(0,385);
              //this.DashboardInfo2 = e.slice(385);

              //var f = e.slice(0,385)
              
              //console.log(this.FTSEplot)
            });

            },
               loadBarcPlot(){
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
               loadMicroPlot(){
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

                instance.get('https://flask-way.herokuapp.com/getMicroFunds')
              //instance.get('https://cors-escape.herokuapp.com/http://flask-way.herokuapp.com')
                .then(response => {
                //   var FIRS,firstStep,respondents;
                // firstStep = JSON.stringify(response.data.ArriaText)
                // respondents = JSON.parse(firstStep);
                // FIRS = JSON.parse(respondents)
                // console.log(FIRS);
              //this.DashboardInfo = respondents;
              
              var c = JSON.stringify(response.data.MicroFunds[0])
              var a = JSON.parse(c);
              var d = JSON.parse(a)
              //var b = a;
              //var b = a.replace(/(<([^>]+)>)/ig,"");
             // var e = b.replace("&nbsp;f","f");
             var  divisor = 10
             for(var i = 0, length = d.length; i < length; i++){
                  d[i] /= divisor;  // `a[i].x /= d` is shorthand for `a[i].x = a[i].x / d`
                  d[i] /= divisor;
              }
              var zc = d;
              //var zc = d.splice(83,180)
              //var z =d.splice(169,180)
              this.MicroFundsplot = zc;
              //var par_2 = e.slice(375)
              //this.DashboardInfo = e.slice(0,385);
              //this.DashboardInfo2 = e.slice(385);

              //var f = e.slice(0,385)
              
              //console.log(this.MicroFundsplot)
            });

               },
               loadSSEPlot(){
                                   
                const instance = axios.create({
                headers: {
                  
                          'Content-Type' : "application/x-www-form-urlencoded; charset=UTF-8",
                          
                        
                },
                });

              delete instance.defaults.headers.common['X-CSRF-TOKEN'];
              delete instance.defaults.headers.common['X-Requested-With'];

             

                instance.get('https://flask-way.herokuapp.com/getSSE')
              
                .then(response => {
                
              var c = JSON.stringify(response.data.SSE[0])
              var a = JSON.parse(c);
              var d = JSON.parse(a)
              
             var  divisor = 10
             for(var i = 0, length = d.length; i < length; i++){
                  d[i] /= divisor;  
                  d[i] /= divisor;
              }
              var zd = d
               
              this.SSEplot = zd;
              
            });

               },
              loadVodaPlot(){
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

                instance.get('https://flask-way.herokuapp.com/getVodafone')
              //instance.get('https://cors-escape.herokuapp.com/http://flask-way.herokuapp.com')
                .then(response => {
                //   var FIRS,firstStep,respondents;
                // firstStep = JSON.stringify(response.data.ArriaText)
                // respondents = JSON.parse(firstStep);
                // FIRS = JSON.parse(respondents)
                // console.log(FIRS);
              //this.DashboardInfo = respondents;
              
              var c = JSON.stringify(response.data.Vodafone[0])
              var a = JSON.parse(c);
              var d = JSON.parse(a)
              //var b = a;
              //var b = a.replace(/(<([^>]+)>)/ig,"");
             // var e = b.replace("&nbsp;f","f");
             var  divisor = 10
             for(var i = 0, length = d.length; i < length; i++){
                  d[i] /= divisor;  // `a[i].x /= d` is shorthand for `a[i].x = a[i].x / d`
                  d[i] /= divisor;
              }
             var ze = d;
             //var ze = d.splice(83,180)
             // var z =d.splice(169,180)
              this.Vodaplot = ze;
              //var par_2 = e.slice(375)
              //this.DashboardInfo = e.slice(0,385);
              //this.DashboardInfo2 = e.slice(385);

              //var f = e.slice(0,385)
              
              //console.log(this.FTSEplot)
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
                //var a = JSON.parse(c);

                var ftseDat = JSON.stringify(response.data.raw_data.ftse)
              
                var actualData = JSON.stringify(response.data.raw_data.acc_value)
                var del_index = JSON.stringify(response.data.raw_data.del_index)
                var del_pf = JSON.stringify(response.data.raw_data.del_pf)
                // var b = a;
                // var b = a.replace(/(<([^>]+)>)/ig,"");
                // var e = b.replace("&nbsp;f","f");
                //this.DashboardInfo = e;
                //var par_2 = e.slice(375)
                var TopArr = [c,ftseDat,actualData,del_index,del_pf]
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
              
              var c = JSON.stringify(response.data.ArriaText[0])
              var a = JSON.parse(c);
              var b = a;
              var b = a.replace(/(<([^>]+)>)/ig,"");
              var e = b.replace("&nbsp;f","f");
              //this.DashboardInfo = e;
              //var par_2 = e.slice(375)
              this.DashboardInfo = e.slice(0,385);
              this.DashboardInfo2 = e.slice(385);

              //var f = e.slice(0,385)
              
              //console.log(DashboardInfo)
            });
          },
          loadNews(){
            this.loadBarclaysNews();
            this.loadMicroFocusNews();
            this.loadSSENews();
            this.loadVodafoneNews();
            this.intervalid1 = setInterval(() => {
                  this.changes = ((Math.random() * 100).toFixed(2))+'%';
                  console.log (this.changes);
                  this.loadBarclaysNews();
                  this.loadMicroFocusNews();
                  this.loadSSENews();
                  this.loadVodafoneNews();
              }, 1800000);
              //1800000 //3000 30 mins
          },
         
          loadBarclaysNews(){
            //console.log ("BarclaysNEWs"); 
            const instance = axios.create({
            headers: {
              //'X-Requested-With': "XMLHttpRequest",
                    //  'Content-Type' : "application/json; charset=utf-8",

                     
                    // 'Access-Control-Allow-Credentials' : "True",
                    //'Access-Control-Allow-Headers' :"Content-Type",
                    //'Access-Control-Allow-Origin' : "*",
                    // 'Access-Control-Allow-Methods' : "GET,HEAD,OPTIONS,POST,PUT",
                      'Content-Type' : "application/x-www-form-urlencoded; charset=UTF-8",
                     
            },
            });

          delete instance.defaults.headers.common['X-CSRF-TOKEN'];
          delete instance.defaults.headers.common['X-Requested-With'];

            instance.get('https://newsapi.org/v2/everything?q=Barclays%20plc&apiKey=421f30907256487aabc6e32e47cbf6f4'
            /*{
                   headers : {
                     'Content-Type' : 'application/json; charset=utf-8',
                     'Access-Control-Allow-Origin' : '*',
                     'Access-Control-Allow-Credentials' : 'True',
                     'Access-Control-Allow-Methods' : 'GET,HEAD,OPTIONS,POST,PUT',
                     'Access-Control-Allow-Headers' :'Content-Type',

                   }
              
            }*/
              ).then(response => {
          this.barclaysNews = response.data;
         // console.log(response.data)
        });
        
        //  axios.get('https://newsapi.org/v2/everything?q=Barclays%20plc&apiKey=421f30907256487aabc6e32e47cbf6f4'     
        //    var url = 'https://newsapi.org/v2/top-headlines?' +
        //           'country=us&' +
        //           'apiKey=421f30907256487aabc6e32e47cbf6f4';
        // var req = new Request(url);
        // fetch(req)
        //     .then(function(response) {
        //         console.log(response.json());
        //     })
          },
          loadMicroFocusNews(){
            //console.log ("BarclaysNEWs"); 
            const instance = axios.create({
            headers: {
              
                      'Content-Type' : "application/x-www-form-urlencoded; charset=UTF-8",
                     
            },
            });

          delete instance.defaults.headers.common['X-CSRF-TOKEN'];
          delete instance.defaults.headers.common['X-Requested-With'];

            instance.get('https://newsapi.org/v2/everything?q=Micro%20Focus%20International%20Plc&apiKey=421f30907256487aabc6e32e47cbf6f4')
            .then(response => {
          this.microFocusNews = response.data;
          //console.log(response.data)
        });
        
        
          },
          loadSSENews(){
            //console.log ("BarclaysNEWs"); 
            const instance = axios.create({
            headers: {
              
                      'Content-Type' : "application/x-www-form-urlencoded; charset=UTF-8",
                     
            },
            });

          delete instance.defaults.headers.common['X-CSRF-TOKEN'];
          delete instance.defaults.headers.common['X-Requested-With'];

            instance.get('https://newsapi.org/v2/everything?q=Scottish%20and%20Southern%20Energy%20plc&apiKey=421f30907256487aabc6e32e47cbf6f4').then(response => {
          this.SSENews = response.data;
          //console.log(response.data)
        });
        
     
          },
                    loadVodafoneNews(){
            //console.log ("BarclaysNEWs"); 
            const instance = axios.create({
            headers: {
                       'Content-Type' : "application/x-www-form-urlencoded; charset=UTF-8",
                     
            },
            });

          delete instance.defaults.headers.common['X-CSRF-TOKEN'];
          delete instance.defaults.headers.common['X-Requested-With'];

            instance.get('https://newsapi.org/v2/everything?q=Vodafone%20Group%20plc&apiKey=421f30907256487aabc6e32e47cbf6f4').then(response => {
          this.VodafoneNews = response.data;
          //console.log(response.data)
        });
        
     
          },


        },
        
        mounted() {
            console.log('Component mounted.')
            this.loadDashboardInfo();
            this.loadNews();
            
            //this.renderChart(this.datacollection, this.options);
            
        },
        
    }
</script>



