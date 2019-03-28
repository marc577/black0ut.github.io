---
layout: default
title: start.
---
<h1 class="text-primary">{{ page.title }}</h1>
<div class="jumbotron">
    <h3>{{ site.github.owner_name }}</h3>
    <div class="container">
        <div class="row">
            <div class="col-md-auto">
                <img style=" width: 50%; display: block;" src="{{site.github.owner_gravatar_url}}" alt="Card image">   
            </div>
            <div class="col">
                    <p class="lead text-primary" id="name"></p>
                    <p id="blog"></p>
                    <p id="email"></p>
                    <p id="company"></p>
                    <p id="loc"></p>
                    <hr class="my-4">
                    <p id="bio"></p>
                    <p class="lead">
                        <a class="github-button" href="{{ site.github.owner_url }}" data-size="large" data-show-count="true" aria-label="Follow @{{ site.github.owner_name }} on GitHub">Follow {{ site.github.owner_name }}</a>
                    </p>
            </div>
            
        </div>
    </div>
</div>
        
<script src="../assets/js/gh3.min.js"></script>
<script>

    var b0ut = new Gh3.User("{{ site.github.owner_name }}");
    var userInfos = $("#user");

    b0ut.fetch(function (err, resUser){

    if(err) {
       throw "outch ..."
    }

    console.log(b0ut, resUser);

    _.each(_.keys(resUser), function (prop) {
        $('#'.concat(prop)).append(resUser[prop]);
    });

      });

</script>
