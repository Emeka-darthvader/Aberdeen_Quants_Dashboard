<template>
<div class="container-fluid">
        <!-- Info boxes -->
        <div class="row">
          <div class="col-12 col-sm-6 col-md-3">
            <div class="info-box">
              <span class="info-box-icon bg-info elevation-1"><i class="fa fa-chart-bar"></i></span>

              <div class="info-box-content">
                <span class="info-box-text">Portfolio profiles</span>
                <span class="info-box-number">
                  4
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
                <span class="info-box-text">Visualizations </span>
                <span class="info-box-number">5</span>
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
                <span class="info-box-number">10% <i class="fas fa-arrow-up green"></i> <i class="fas fa-arrow-down red"></i></span>
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
                <span class="info-box-number">5% <i class="fas fa-arrow-up green"></i> <i class="fas fa-arrow-down red"></i> </span>
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
                      <img src="img/graphs.png" class="card-img-top">
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
                    <p>
                      The market for [fund name] has increased from [last price] to [price change]. The predicted value for this fund is
                      [ML predicted value]. Your total cost of portfolio is [total_cost] and current value of portfolio is [value].
                      Your net profit since [date] is [profit value]. Marc recommends you to buy more shares for this [company].
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
    export default {
        data(){
          return{
            barclaysNews:{},
            microFocusNews:{},
            SSENews:{},
            VodafoneNews:{},
          }
        },
        methods:{
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
            this.loadNews();
        },
        
    }
</script>
