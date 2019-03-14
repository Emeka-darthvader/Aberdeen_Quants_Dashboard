<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-12">
                <div class="card" style="width: 18rem;">
                <img src="img/O875DT0.jpg" class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">Chat with our Chatbot</h5>
                    <p class="card-text">Hi I'm MARC, Click the link to open our messenger and chat with our AI assistant 😉.</p>
                    <div>
                         <div><!--<a href="#" class="btn btn-primary" target="_blank"><i class="fab fa-facebook-messenger"></i> Open Messenger</a>--></div> 
                        <div><a href="https://www.freepik.com/free-photos-vectors/people">People vector created by smithytomy - www.freepik.com</a></div>
                    </div>
                    
                    
                    <!-- <a href="#" class="btn btn-primary">Go somewhere</a> -->
                </div>
                </div>
                <!-- Load Facebook SDK for JavaScript -->
                <div id="fb-root"></div>
                

                <!-- Your customer chat code -->
                <div class="fb-customerchat"
                attribution=setup_tool
                page_id="246412539632958">
                </div>
      
            </div>
        </div>
    </div>
</template>



<script>
    export default {
        mounted() {
            console.log('Component mounted.')
              
        }
    }
</script>    


<script>
    window.fbAsyncInit = function() {
                FB.init({
                xfbml            : true,
                version          : 'v3.2'
                });
            };

            (function(d, s, id) {
            var js, fjs = d.getElementsByTagName(s)[0];
            if (d.getElementById(id)) return;
            js = d.createElement(s); js.id = id;
            js.src = 'https://connect.facebook.net/en_GB/sdk/xfbml.customerchat.js';
            fjs.parentNode.insertBefore(js, fjs);
            }(document, 'script', 'facebook-jssdk'));
</script>




