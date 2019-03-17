<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-12">
                <div class="jumbotron">
                <h1 class="display-4">Hello, Dear Customer</h1>
                <p class="lead">We value the services we offer to you and would appreciate if you went through the terms and conditions</p>
                <hr class="my-4">
                <p>Kindly click the link below to visit our terms and conditions...</p>
                <a class="btn btn-primary btn-lg" href="#" role="button">Click to download full document</a>
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




