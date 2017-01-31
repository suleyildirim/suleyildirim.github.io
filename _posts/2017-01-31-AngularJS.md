---
layout: post
title: AngularJS
permalink: /Home/Genel/AngularJS
summary: Merhaba arkadaslar, bu yazımızda AngularJS temel kavramları öğreneceğiz.
---

# AngularJS Giriş Ve Temel Kavramlar

* <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>  Kütüphanesi eklenmeli.
* HTML içinde ng-app attribute eklenmeli
* Ng-app Angular yönlendiricidir.
* Ng, Angular için kısaltmadır. (ngStorage, ng-conf, ng-Book)

{% highlight java %}
<div ng-app>
This area controlled by Angular!
</div>
{% endhighlight %}

---
{% highlight java %}
<!DOCTYPE html>
<html>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>

<div ng-app>
<p>My first expression: {{ 5 + 5 }}</p>
</div>

</body>
</html>
{% endhighlight %}

{{ 5 + 5 }} angular matematiksel işlem olarak anlayıp ekrana 10 yazdırır.
<div ng-app> yerine <div> yazarsak; My first expression: {{ 5 + 5 }} ekrana yazdırır.
<body ng-app> yazılırsa angular olarak işlem yapılır.


## JavaScript Patterns

1. Functions as abstractions
	
{% highlight java %}
var work = function () {
console.log("working hard!");
};
    work();
{% endhighlight %}
    
---

{% highlight java %}
var work = function () {
        console.log("working hard!");
    };
    var doWork = function (f) {
        f();
    };
    doWork(work);
 {% endhighlight %}
 
    2. Functions to build modules
    
{% highlight java %}    
var createWorker = function () {

        var workCount = 0;
        var task1 = function () {
            workCount += 1;
            console.log("Task1 " + workCount);
        };
        var task2 = function () {
            workCount += 1;
            console.log("Task2 " + workCount);
        };
        return {
            job1: task1,
            job2: task2
        };
    };

    var worker = createWorker();

    worker.job1();
    worker.job2();
    worker.job2();
    worker.job2();
    //worker.task1(); çalışmaz (global olmadığı için)
 {% endhighlight %}
 
3. Function to avoid global variables : Immediately invoked funcction expression (IIFE) – pronouced as “iffy”
  {% highlight java %}
(function () {
        var createWorker = function () {

            var workCount = 0;
            var task1 = function () {
                workCount += 1;
                console.log("Task1 " + workCount);
            };
            var task2 = function () {
                workCount += 1;
                console.log("Task2 " + workCount);
            };
            return {
                job1: task1,
                job2: task2
            };
        };

        var worker = createWorker();

        worker.job1();
        worker.job2();
        worker.job2();
        worker.job2();

    }());
    {% endhighlight %}
    






