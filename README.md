Magento Resize Category Images
==============================

[![Flattr this git repo](http://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/submit/auto?user_id=dbashyal&url=https://github.com/dbashyal&title=Github Repos&language=&tags=github&category=software)

This is a free magento extension/module to resize category images. 
Join the converstation at: 
[How to resize Magento e-Commerce category images](http://dltr.org/blog/magento/121/How-to-resize-Magento-e-Commerce-category-images)

## How to use this?

	/*
	 * You can pass width and height and much more, see helper for details.
	 * echo $this->helper('timage')->init($_category->getImageUrl())->resize(null, 120)
	 * echo $this->helper('timage')->init($_category->getImageUrl())->resize(120, null)
	 * echo $this->helper('timage')->init($_category->getImageUrl())->resize(120, 120)
	 */
	<div class="product-image">
		<a href="<?php echo $_category->getURL() ?>" title="<?php echo $this->htmlEscape($_category->getName()) ?>">
			<img src="<?php echo $this->helper('timage')->init($_category->getImageUrl())->resize(null, 120) ?>" alt="<?php echo $this->htmlEscape($_category->getName()) ?>"/>
		</a>
	</div>
	
# How to crop image?
You can init image helper with path to image, then  you must pass width and height to crop image. After image is cropped its saved and ready to be resized using cropped image as source image to be resized. See example code below.

```PHP
<img src="<?php 
	echo $this->helper('timage')
			  ->init($_category->getImageUrl())
			  ->setWidth(230)
			  ->setHeight(200)
			  ->crop()
			  ->resize() 
	?>" alt="alt text"/>
```

###visit: dltr.org for more [Magento Tips, Tricks and Free Extensions](http://dltr.org/).
