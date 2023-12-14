#### :peach: javascript

## Sticky Nav

```js
    <script>
  let tabContainerHeight = 70;
  let currentTab;
    $('.el-hero-tab').click(function() { 
        onTabClick(event, $(this))
    });

 function onTabClick(event, element){
            event.preventDefault();
            let elementLeft = element.offset().left;
            elementLeft = Math.floor(elementLeft)
            let clickedTab = element.attr('href');
            let goSection = $(element.attr('href')).offset().top - tabContainerHeight+1;
     
            $('body, html').animate({
                scrollTop: goSection
                }, 750);
            sliderCss(element, elementLeft)
     } 

  function sliderCss(slider, left){
      let width=0;
      width=$(slider).css('width')
      $('.el-hero-tab-slider').css('width', width)
      $('.el-hero-tab-slider').css('left', left)
  }
    
    function findCurrentSeletor(){
        $('.el-hero-tab').each(function(){
        let id= $(this).attr("href");
        let offsetTop =     $(id).offset().top - tabContainerHeight;
        let offsetBottom =  $(id).offset().top + $(id).height() - tabContainerHeight;             

        if ($(window).scrollTop() > offsetTop && $(window).scrollTop() < offsetBottom) {
                currentTab = this;
                sliderCss(currentTab,  $(currentTab).offset().left)
         }

        })
    }
    function checkTabContainerPosition(){
        let offset = $('.el-hero-tabs').offset().top + $('.el-hero-tabs').height()-tabContainerHeight ;
        let windowScoll = $(window).scrollTop();
            if(windowScoll > offset) {
            $('.el-hero-tabs-container').addClass('el-hero-tabs-container--top')
            } else {
                $('.el-hero-tabs-container').removeClass('el-hero-tabs-container--top')
            }
        }

      $(window).on('scroll resize',function(){
        $('.el-hero-tab').each(function(){
         
        })
        findCurrentSeletor();
        checkTabContainerPosition() 
       })
        </script>
```


