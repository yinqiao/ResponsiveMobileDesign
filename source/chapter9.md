# RESPONSIVE IMAGES
# 第9章 响应式图片

Designs will always be epic, iconic, and awe inspiring. However, when thinking about the medium that users will be viewing your design on, it might be best to save some of that awe for the details and content delivery speed.Using images that work on a variety of devices can be challenging. Luckily, you can start using some techniques and solutions to take your design into the future.￼￼￼￼￼￼

设计创作总是史诗般、生动形象、富于灵感的。然而，一旦考虑到用户查看你的创作所使用的设备，
为了细节和内容的呈现速度最好还是少一些敬畏感。

在各式各样的设备商使用图片是很有挑战性的。幸运的是，你可以开始使用一些技术和解决方案来为未来设计。

## Images Should Be Responsive
## 图片应该是响应式的

It used to be that the most difficult part of exporting an image was deciding whether it worked better as a JPEG or GIF file. Those were simple days when it usually came down to determining the number of colors used and deciding whether transparency was important to me.

过去，导出图片最难的问题是决定使用JPEG格式还是GIF格式更好。不过，通常确定了图片使用的颜色数量、确定了图片透明度的重要性之后，这些问题都已经简单了。

Then came PNG files, the solution that delivered the grandeur and scope of JPEG files and also gave images crisp and pristine transparency. It was definitely a step up, and many designers and developers still rely heavily on using PNG files. However, the file size for large images still leaves something to be desired. PNG files offer the same number of colors as JPEG files, but the file size ends up being far greater than with JPEG files because of the lossless compression that PNG uses in many image-manipulation programs. You might be able to save space by switching to a lossy PNG file, but JPEG files will almost always be smaller when used on complex, high- color images. As designers and developers, we are now dealing with incorporating SVG files and WEBP files.

然后是PNG文件，解决方案是确定壮丽辉煌JPEG文件，同时设置好图像清晰度和原始透明度。这无疑是艰难的一步，并且许多设计师和开发者仍然严重依赖PNG文件。然而，对于大型图像的文件大小仍然令人不满意。当PNG文件采用与JPEG文件相同的一些颜色值时，其文件大小比JPEG文件大非常多，原因是PNG在许多图像处理程序中使用无损压缩。你可以通过开启PNG的有损模式以节省空间，但是当使用更为复杂的、真彩色图像时，JPEG文件仍然比有损压缩的PNG文件小很多。作为设计师和开发人员，我们正在解决将SVG文件和WEBP文件合并的问题。

All of these image formats are fantastic in their own respects, but the problem is dealing with them when they are too big or too small for the screen requesting them.

从这些图片格式自身的角度来看，它们都是极为出色的，但是问题是对于展示图片的屏幕来说，这些图片太大或太小了。

To give you an understanding of why images need to be responsive, in this chapter, you learn about delivering images to the browser by means of scaling, using new image elements, and using JavaScript to serve the correct image.

为什么图片要做响应式？本章你将学会通过缩放、使用新的图像元素、使用JavaScript等方法在浏览器端展示合适的图片。

## 图片分发

When you are dealing with mobile devices, the images that you choose to use are extremely important. Detail, clarity, and even the emotion you are attempting to evoke can be dramatically shifted when your image is squished or broken on the page.

当你正在处理移动设备，你所采用的图片非常重要。当你使用的图片在页面上显示为变形或被截断，细节、清晰、甚至你想表达的情感会被毫无疑问地曲解了。

To give you a feel for what I am talking about, see Figure 9.1.
In Figure 9.1, you can easily see both the climber in the middle and the crowd below. If you viewed this same image on a phone, the scene either would be zoomed in or would have to scale to fit, as in Figure 9.2.
The image has been scaled so that everything is still visible, but this leaves less initial detail, especially on the climber, and might actually cause more visual confusion than would a different image.

为了更为明确我想说什么，请看吐9.1。在图9.1中，你可以很容易地看到中间的登山者和下面的人群。如图9.2所示，如果在手机上看同一张图片，屏幕会被放大或缩小以适配图片的大小。图片被缩小了以便保证所有的图片内容是可见的，但是这使得原始图片细节、尤其是登山者，事实上也有可能产生了更多视觉混乱误以为是另一张图片。

Figure 9.1 The image is viewed on a desktop with everything in good detail.

图9.1 在台式机上展示的图片所有细节完好

Figure 9.2 When viewed on a phone, the scene is scaled to fit, making the subject more difficult to view.

图9.2 图片在手机上展示，屏幕被缩放以适配图片，使得主题无法辨识

Leaving the visuals aside, what does this do for users who are attempting to download the images? Well, for starters, it slows them down. The original image used for Figures 9.1 and 9.2 is a JPG that comes out at 344KB. That certainly doesn’t sound like much, but when your site has 10 images of a similar size, you would be adding more than 3MB in images alone to what users have to download on their mobile devices, along with any JavaScript files and other data to view your site.

除了视觉效果不说，在用户试图下载图片时都发生了什么呢？嗯，首先，慢了下来。图9.1和图9.2使用的原始图片是344KB的JPG文件。当然，听起来好像不多，但是，当你的网站有10张相同大小的图片，这将给用户增加了3MB的图片需要下载到他们的移动设备商，同时还需要下载JavaScript文件和你的网站上的其他数据。

Note

3MB of data doesn’t sound very large when you have a fast broadband connection. However, that same 3MB of data can take up some time (as well as data) on wireless plans. The following lists the time to download a 3MB image:

■ 3G (1–4Mbps): 5–23 seconds
■ LTE (5–10Mbps): 2–4 seconds
■ DSL (1.5Mbps): 15 seconds

Note that, even after downloading the image, the device still has to process and display the image. If you have multiple images, the time taken to load images will add up quickly.

注意：

当你链接至高速带宽上时，3MB的数据量听起来不是非常大。然而，在无线网络上，下载3MB的数据需要耗费一定的时间和数据空间。以下是下载3MB大小的图片所耗费的时间：

* 3G(1-4Mbps): 5-23秒
* LTE (5–10Mbps): 2–4秒
* DSL (1.5Mbps): 15秒


If you were able to serve a different image based on device size, this would not only save in file size, but it would also enable you to choose the art direction of the image. Figure 9.3 shows the image optimized for mobile users.

如果你能够根据设备大小提供不同的图像，不仅保存文件大小，而且让你能够选择图像的艺术导向。图9.3展示了为移动用户优化后的图片。

Being able to choose exactly what is shown is helpful, and because this enables you to use a smaller image (this one is 49KB), you can be assured that the user will be able to download and view the image much faster.
While on the subject of the file size of your images, it might be worth using the WEBP image format on your site. This format has a wide array of features and uses a different compression algorithm, enabling you to save anywhere from 7% to 50% of original picture size. Figure 9.4 shows WEBP and JPEG images.

能够精确地选择展示什么图像是非常有用的，因为这让你能够选择更小的图片（这一张是49KB），你能够确保用户更加快速地下载并查看图片。说到图片的大小问题，在你的网站上值得使用WEBP格式的图片。

You have a few methods that you can employ to do what we have done here. In the next sections, you learn first about image scaling, then about using the srcset attribute, and then about using the picture element.

实现我们这里所做的，你可以采用几种方法。下一节中，你将首先学习图片缩放，其次学习使用srcset属性，最后学习使用图片元素。

Figure 9.3 The visible portion of the image has changed for an optimal viewing experience on a mobile device.

Figure 9.4 Using WEBP, the top image is 56KB; the JPG image on the bottom is 111KB.

图9.3 为了实现在移动设备的最佳体验，图片的可视部分发生了变化。

图9.4 上面一张图片使用WEBP格式，其大小是56KB；而下面一张采用的是JPG格式，其大小是111KB。

## Image Scaling

## 图片缩放

One of the most common—and also most misunderstood—“responsive” image techniques is the use of image scaling via the browser. This doesn’t involve any new images; it just requires a few lines of CSS. Applying the following in your CSS magically makes your images shrink to fit:

img {
max-width: 100%; height: auto;
}

一种最常见——也是最容易误解——“响应式”图片技术是通过浏览器缩放。这不需要任何新图片，仅仅需要几行CSS代码。在你的CSS中添加如下代码，将魔术般地使得你的图片进行缩放适配：

		
		
	img {
		max-width: 100%; height: auto;
	}


Note that IE8 users will notice a spectacular amount of fail with this example; to fix it, you should apply width: 100% before max-width: 100%.You should also be aware that, by setting an image to have a width of 100%, the image might attempt to take up as much space as possible. This means potential stretching. To avoid this, be sure to put the image inside a container such as a <div> element that has a width already set.

需要注意的是，使用本例在IE8浏览器中会发现惊人的失败。为了修复IE8，你必须在max-width: 100%之前使用width: 100%。你还需注意的是，通过设置图片的宽度为100%，图片将试图尽可能占用更大的空间。这意味着潜在的拉伸效果。为了避免这种情况，请确保图片元素在如<div>这类自身带有宽度的元素中。

This will make all your images fit the screen they are viewed on, but it does nothing for file size. On top of the included file size, using large images and forcing the browser to scale can be CPU and memory intensive. That might not matter too much with your desktop or laptop computer, but it quickly becomes a very real problem when looking at rendering speed and power consumption on a mobile device.

这将使得你的图片适配所视屏幕，但是图片的大小并未发生变化。另外，使用大图并让强制使得浏览器进行缩放，可以提交CPU和内容的使用率。在台式机或笔记本电脑商可能看不出有多大的影响，但是当在移动设备上查看图片的渲染速度和耗电量将很成问题。

Tip

If you are currently using image maps on your site, you will need to come up with a new solution. Because of the pixel-perfect mapping of image maps, images that are resized will no longer have targets in the places you expect. You can work around this by positioning invisible hot spots on the image by using a percentage for layout, but this is far from a bulletproof solution.

小贴士：

如果你的网站正在使用图片映射，那么你需要想出一个新的解决方案。因为，图像映射是像素级的映射关系，一旦图片尺寸发生变化，那些映射将无法定位到你所预期的位置。当然，你可以通过百分比布局放置不可见热区来解决，但这远不是一个完美的解决方案。

I do not advocate the use of browser-resized images by giving the browser a large image and forcing it to handle scaling the displayed size as a standard practice in your design; however, it can be a last-minute solution to get you by until you can get the correct images or solution in place.

我并不提倡将这种方法作为你的设计的标准的实践：通过提供一张大图给浏览器，让浏览器来改变这张图片的尺寸和处理缩放展示尺寸。不过，这可以是一个最后的解决方案，直到你找到正确的图像或解决方案。

### Using Intrinsic Ratio

### 使用固定比例

Maybe this has happened to you: You’re browsing the web and start to load a page, but as you begin reading, the content is suddenly moved or shoved in a new direction as images are loaded. This is called page reflow and is caused by images being loaded in a place that did not already adjust the layout to handle them. Figure 9.5 shows a page before and after images are loaded, to illustrate this effect.

或许你也曾遇到过这种场景：你正在浏览网页并开始加载页面，但是当你开始阅读时，当图片下载完成后网页的内容突然被移动或推挤到一边。这就是网页重绘，这种情况是由于在某处并未调整布局处理下载完成的图片而引起的一种重绘。图9.5展示了一张网页在图片下载完成前后的效果。

Figure 9.5 Before images are loaded, text content is allowed to bunch up (left). After the image has loaded, the text moves below the image (right).

图9.5 左图展示的是在图片下载完成前，文本内容可以聚集在一处。右图展示的是当图片下载完成后，文本内容被推移到图片下方。

You might be thinking, “Well, of course the text moved! I can’t define how the space of an image changes on every screen!” That’s true, you definitely cannot. However, if you know the ratio of that image, you can use a little trick to determine how much space the image will take up in this particular layout.

你或许会想，“文字当然会被移动！我无法定义所有屏幕上图片的尺寸！”是的，你确实不能。不过，如果你知道图片的比例，就可以使用一点小技巧来确定在这种特殊布局中该图片所需占用的空间大小。

Thierry Koblentz first talked about the intrinsic ratio on A List Apart in 2009 (http://alistapart.com/article/creating-intrinsic-ratios-for-video/). In the article, Thierry talks about using the intrinsic ratio for handling videos on websites. It also happens to work quite well for images that need to use a placeholder to stop page reflow.

Thierry Koblentz 早在2009年在A List Apart网站(http://alistapart.com/article/creating-intrinsic-ratios-for-video/)上发表文章提出了这种技巧。在这篇文字中，Thierry讨论了在网站上使用这种技巧来处理视频。在需要提供一个占位来组织页面重绘的情况下，使用这种技巧效果也非常好。

To see this in action, Figure 9.6 shows the same page, but with a plan for the page reflow by including space for the image by using the intrinsic ratio of the image. This is noticeable in com- parison to Figure 9.5 because the text “This text should appear below...” is not visible on the screen when the page initially loads; instead, you only see the “An image should appear below” as the page has now saved space to insert the image.

举一个例子来说明：图9.6展示了同一张网页，

Figure 9.6 Space has been reserved (left) for the image to load into (right).


To figure out the intrinsic ratio, you need to know the aspect ratio of your image, divide the second number by the first, and use the result as padding on a container element.
For example, if you have a 480x320px image, the aspect ratio is 3:2. Taking that ratio, you get the value of 2/3, or 66.67. With this number, you can now set up a container element that will be used as a placeholder for the image. The CSS looks like this:
.wrapper {
position: relative; padding-bottom: 66.67%; height: 0;
}
.image {
position: absolute; top: 0;
left: 0;
width: 100%; height: 100%;
}


When using intrinsic ratios, you need to create multiple classes for each aspect ratio you use with your images. This way, you can have differently sized images and still have placeholders for them.
The srcset Attribute
If you have rather sanely decided that scaling images is not something you’d like to pursue, you might be interested in using the srcset attribute.
This attribute is used with the img element and is quite elegant in the execution of choosing the correct image to display.
Look at the following snippet:
<img src="meh.jpg" alt="an image" />
Yes, that is the ordinary way to add an image to your site. It has an src attribute that specifies which file to use (in this case, the aptly named meh.jpg), and the alt attribute enables you to add text that will appear if the image is unavailable, for text readers, and for similar uses.
The following snippet has had the srcset attribute added:
<img src="standard.jpg" alt="an image"
srcset="small_480.jpg 480w, standard_768.jpg 768w,
large_1024.jpg 1024w, large@2x.jpg 2x" />
Tip
Use a naming convention with your images. The previous snippet of srcset uses a bit of humor to help convey that you can use larger images with more detail as the screen gets larger, but you should not copy those naming standards. Attempt- ing to manage a large number of files with names that do not match will be tricky and, in the long run, not worth the stress. Using names such as hero_480.jpg and hero_480@2x.jpg is a much better system.
You can see from the previous example snippet that the srcset attribute takes a list of comma-separated values. They might seem a little out of sorts at first, but at second glance, you should notice that there is a value ending with w after almost every image filename. That value tells the browser the size or limit of showing that image.





That breaks down into the following:
■ 0–480px screens will show small_480.jpg.
■ 481–768px screens will show standard_768.jpg.
■ 769–1024px screens will show large_1024.jpg.
■ High-pixel-density screens will show large@2x.jpg.
■ All other screens will use standard.jpg.
This is a fantastic solution, but use it with careful planning to make sure that you are serving optimized images to the correct devices. Having a fallback image is nice, but it could leave you with an image that is either too small or too large to fit the device that triggered the fallback.
You might also want to be careful when using the element because it has been implemented only in WebKit-based browsers and Chrome 34+.
With a little luck, other browsers will start supporting the attribute soon. If you find that you cannot contain your excitement and you need to use it now, you or your developer can use a polyfill (https://github.com/borismus/srcset-polyfill) to fill in the gap and start using srcset now.
The picture Element
Another proposed solution for responsive images is a new element that will be used in concert with the img element. The goal of this element is to provide a way for images to be displayed based on device specifics and media queries.
Listing 9.1 demonstrates how the picture element could be implemented into a site.



Listing 9.1 Using the picture Element
￼￼￼￼01
02
03
04
05
06
<picture>
<source srcset="small.jpg">
<source media="(min-width: 480px)" srcset="mid.jpg 1x, mid@2x.jpg 2x"> <source media="(min-width: 768px)" srcset="large.jpg">
<img src="default.jpg" alt="The image">
</picture>


The way the picture element works is really quite fascinating. The element acts as a wrapper that uses source elements as well as an img element. Use of the img element helps browsers that do not currently support the picture element render an image.
The source element is used for setting up parameters that define what image should be rendered. On line 2, the srcset attribute is used to define an image that will be displayed on screens that measure from 0px and up. It does not cover all screen sizes because of the source elements that are defined on lines 3 and 4.


On line 3, you can see that a media attribute has been used to define the image that devices with a minimum screen size of 480px will render. It also contains the srcset attribute that defines a high-pixel-density image if the device supports it.
Looking ahead to line 4, you can see that the media attribute has been used again to define what image devices with a minimum screen resolution of 768px will see.
To break this down, the images will display as follows:
■ Devices with a screen width of 0–479px will load small.jpg.
■ Devices with a screen width of 480–767px will load either mid.jpg or mid@2x.jpg, depending on pixel density.
■ Devices with a minimum width of 768px will load large.jpg.
■ Browsers that do not support the picture element will load default.jpg.

It might also be somewhat surprising to see the srcset attribute inside the source element or even find it supported. It is actually encouraged to help deliver the proper image to the browser.
There is more to using the picture element than just specifying which images to use and using media queries to decide. You can also do some limited feature support testing with it to deliver images based on the browser supporting the image format.
You might be thinking that if a browser is “modern” enough to support the picture element, then it surely must have support for all picture formats. I can easily see why you might have gone down that path in your thinking, but you need to remember that not all browsers support the WEBP image format yet (for a current list, visit http://caniuse.com/webp).
Using the type attribute, you can specify whether an image should be displayed based on browser support. Listing 9.2 shows how this is possible.



Listing 9.2 Specifying Different Animated Image Formats
IMAGES SHOULD BE RESPONSIVE 123
￼￼￼￼01 02 03 04 05
<picture>
<source type="image/webp" srcset="funny.webp"> <source type="video/png" srcset="funny.apng"> <img src="funny.gif" alt="absolute madness" />
</picture>


Looking closely at Listing 9.2, you can see that the type attribute is used on lines 2 and 3. On line 2, it contains a value of image/webp, and line 3 contains a value of video/png. Unless you are the type of designer who regularly tweaks your web server, these values might appear to be utter nonsense. These values are known as a MIME type.
The server and browser use the MIME type to communicate and describe the file that is being transferred and rendered. The image/webp value explains that the file is an image of the WEBP variety. The browser already has a list of known MIME types and decides whether it should
use that file. The value of video/png might appear wrong, but that is the valid MIME type for animated PNG files.
Chrome supports the WEBP image format (including animated WEBP files), but Firefox does not. Firefox does support animated PNG files, however, and other browsers support animated
GIF files.
By using the picture element to specify which image to use, you can optimize the experience for mobile and desktop users.
At the time of this writing, the picture element is not currently supported in any browser. However, there is a project underway for both Firefox and Chrome browsers to have support implemented hopefully before the end of 2014.
To learn more about the picture element, including how to load multiple images for multiple sizes in a more streamlined fashion, visit http://picture.responsiveimages.org/.
Using a JavaScript Solution
Designers and developers who are unable to work with modern browsers, or who do not have the time for the rest of the world to catch up with technology, will be using a JavaScript solution as part of their progressive enhancement suite.
Picturefill, from Scott Jehl, has seen excellent success. I have also created and used my own solution, called Pixity, on several projects.
Picturefill
The problem with the picture element is that, if you want to use it now, you can’t. Even with browsers adding support for it in the near future, you are bound to users actually using that particular browser and having it work on their mobile devices.
This is the problem Scott Jehl saw, so he decided to implement a JavaScript solution that is based on the picture element but uses span elements to allow it to work safely cross-browser.


Note that Picturefill works best with browsers that support CSS3 media queries. With most smartphones, this should not pose a problem because almost all support CSS3 today.
Listing 9.3 shows the HTML markup needed to use Picturefill in your project.


Listing 9.3 Specifying Different Animated Image Formats
01 <span data-picture data-alt="description of image">
02 <span data-src="small.jpg"></span>
03 <span data-src="medium.jpg" data-media="(min-width: 480px)"></span>
04 <span data-src="large.jpg" data-media="(min-width: 768px)"></span>
05 <span data-src="extralarge.jpg" data-media="(min-width: 1140px)"></span>
06
07 <noscript>
08 <img src="small.jpg" alt="description of image">
09 </noscript>
10 </span>


Lines 2–5 show the initial setup required to make Picturefill work on browsers that support JavaScript, and lines 7–9 show the image that will be shown on devices that do not support JavaScript.
Line 1 uses data attributes of data-picture and data-alt Picturefill uses to determine where the image will be placed and what text will be used as the image’s alternate message for screen readers and similar devices.
The other lines contain at least a data attribute of data-src. Others have an accompanying data-media that specifies the image that should be used and the requirements for displaying that particular image.
If you review both the srcset and picture element sections, this should start looking very similar in execution. You might be wondering about high-pixel-density screens and how
they fit into the equation. They are added by changing the media query in the data-media attribute. Let’s copy and modify a line so that it will serve a high-density image. Note that I have broken the line out to make it easier to read:
<span
data-src="medium@2x.jpg"
data-media="(min-width: 480px) and (min-device-pixel-ratio: 2.0)">
</span>
This could now be added as line 4, and support for high-pixel-density devices would be added for devices between 480px and 767px wide.
To download Picturefill and read the full usage guide, visit https://github.com/scottjehl/ picturefill.

Pixity
Before I saw Picturefill, I was working on a redesign of an eCommerce site that now has more than 40% mobile users.
Knowing that the site is somewhere between 60% and 70% images, I needed a solution that gave me the flexibility of serving different files to different screen sizes but also allowed the content manager an easy way to specify images without having development constantly hard- coding the images into the dynamic files.
The solution was to create a plugin called Pixity. The first use of the plugin was actually to specify when to use high-pixel-density images; that is where the name originated, the PIXel densITY.
Pixity currently is released as a jQuery (1.7+) plugin and is fairly easy to implement. By adding a few data attributes to an img element and giving the image a specific class, the Pixity plugin runs on page load and replaces a small 1x1 pixel image with the appropriate image for the device.
Listing 9.4 demonstrates the HTML markup of an image using Pixity.


Listing 9.4 Using Pixity to Display an Image
<img class="pixity" src="images/placeholder.gif" alt="image description" data-path="images/" data-sm="small.jpg" data-md="medium.jpg" data-lg="large.jpg" data-xl="xlarge.jpg" />


Unlike Picturefill and srcset, you do not specify the minimum device widths for your images. Instead, they are predefined.
By default, the sizes for the images used are as follows:
■ data-sm: 0–480px
■ data-md: 481–767px
■ data-lg: 768–959px
■ data-xl: 960px+
You can change the defaults by modifying the jQuery call like so:
$.pixity({limitSm:600,limitMd:960,limitLg,1280});

Note the data-path attribute. This attribute might seem a bit out of place, but it is quite use- ful with a CMS system with a limited amount of characters. If you are using a CDN with a long directory path, instead of putting it in for every image, you put it in once and then fine-tune it with the other data attributes.
Tip
When using Pixity, you should use an intrinsic ratio if at all possible. Because of the use of a small placeholder image, failing to use an intrinsic ratio will cause the page to reflow on the user.
If you are interested in modifying and editing JavaScript, you can modify and extend Pixity to fit your needs. I have several versions that have not been uploaded to GitHub that I use to work with loading dynamic and responsive content into sliders, and one version allows the client to download the high-pixel-density version of a file only if the client passes a speed test.
Pixity Core is currently licensed as MIT (http://opensource.org/licenses/MIT) and is available for download and modification at https://github.com/dutsonpa/pixity.




Summary
In this chapter, you learned that displaying images takes planning and care. By taking the time to fine-tune the images that will be displayed to users, you increase the chance of them using and returning to your site.
You learned that you can take advantage of art direction to change the visual message you are sharing. You can do this with some new features, such as the srcset attribute, or by taking advantage of JavaScript plugins such as Picturefill and Pixity.

