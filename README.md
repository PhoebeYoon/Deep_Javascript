#### :peach: javascript

## Sticky Nav

### 함수로 구현 
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

### class 구현
```js

class StickyNavigation {
	
	constructor() {
		this.currentId = null;
		this.currentTab = null;
		this.tabContainerHeight = 70;
		let self = this;
		$('.el-hero-tab').click(function() { 
			self.onTabClick(event, $(this)); 
		});
		$(window).scroll(() => { this.onScroll(); });
		$(window).resize(() => { this.onResize(); });
	}
	
	onTabClick(event, element) {
		event.preventDefault();
		let scrollTop = $(element.attr('href')).offset().top - this.tabContainerHeight + 1;
		$('html, body').animate({ scrollTop: scrollTop }, 600);
	}
	
	onScroll() {
		this.checkTabContainerPosition();
    this.findCurrentTabSelector();
	}
	
	onResize() {
		if(this.currentId) {
			this.setSliderCss();
		}
	}
	
	checkTabContainerPosition() {
		let offset = $('.el-hero-tabs').offset().top + $('.el-hero-tabs').height() - this.tabContainerHeight;
		if($(window).scrollTop() > offset) {
			$('.el-hero-tabs-container').addClass('el-hero-tabs-container--top');
		} 
		else {
			$('.el-hero-tabs-container').removeClass('el-hero-tabs-container--top');
		}
	}
	
	findCurrentTabSelector(element) {
		let newCurrentId;
		let newCurrentTab;
		let self = this;
		$('.el-hero-tab').each(function() {
			let id = $(this).attr('href');
			let offsetTop = $(id).offset().top - self.tabContainerHeight;
			let offsetBottom = $(id).offset().top + $(id).height() - self.tabContainerHeight;
			if($(window).scrollTop() > offsetTop && $(window).scrollTop() < offsetBottom) {
				newCurrentId = id;
				newCurrentTab = $(this);
			}
		});
		if(this.currentId != newCurrentId || this.currentId === null) {
			this.currentId = newCurrentId;
			this.currentTab = newCurrentTab;
			this.setSliderCss();
		}
	}
	
	setSliderCss() {
		let width = 0;
		let left = 0;
		if(this.currentTab) {
			width = this.currentTab.css('width');
			left = this.currentTab.offset().left;
		}
		$('.el-hero-tab-slider').css('width', width);
		$('.el-hero-tab-slider').css('left', left);
	}
	
}

new StickyNavigation();

```

