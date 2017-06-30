<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <!-- <link rel="stylesheet" type="text/css" href="css/common.css"> -->
    <!-- <script src="js/common.js" charset="utf-8"></script> -->

  <style type="text/css">
  .circle { width: 70px; height: 70px; position: relative; border-radius: 50%; background: #0cc; }
   .pie_left, .pie_right { width: 70px; height: 70px; position: absolute; top: 0;left: 0; }
   .left, .right { display: block; width:70px; height:70px; background:#efefef;
     border-radius: 50%; position: absolute; top: 0; left: 0;

     /*transform: rotate(30deg);*/
    }
   .pie_right, .right { clip:rect(0,auto,auto,35px); }
   .pie_left, .left { clip:rect(0,35px,auto,0); }
   .mask { width: 64px; height: 64px; border-radius: 50%; left: 3px; top: 3px;
     background: #FFF; position: absolute; text-align: center; line-height: 60px; font-size: 20px; }
  </style>

    </head>
  <body>
    <div class="circle">
      <div class="pie_left">
        <div class="left">
        </div>
      </div>
      <div class="pie_right">
        <div class="right">
        </div>
      </div>
      <div class="mask">
        <span>10</span>%
      </div>
    </div>
    <div class="circle">
      <div class="pie_left">
        <div class="left">
        </div>
      </div>
      <div class="pie_right">
        <div class="right">
        </div>
      </div>
      <div class="mask">
        <span>6.87</span>%
      </div>
    </div>



    <script src="js/jquery-3.2.1.min.js" charset="utf-8"></script>
    <script type="text/javascript">
      $(function() {
       $('.circle').each(function(index, el) {
         var num = $(this).find('span').text() * 3.6;
         console.log(num);
         if (num<=180) {
           $(this).find('.right').css('transform', "rotate(" + num + "deg)");
        } else {
           $(this).find('.right').css('transform', "rotate(180deg)");
           $(this).find('.left').css('transform', "rotate(" + (num - 180) + "deg)");
         };
       });
     });
    </script>
  </body>
</html>
