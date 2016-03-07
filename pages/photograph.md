---
layout: page
title: photograph
---
<link rel="stylesheet" href="../assets/css/blueimp-gallery.min.css">

<!-- The Gallery as lightbox dialog, should be a child element of the document body -->
<div id="blueimp-gallery" class="blueimp-gallery">
    <div class="slides"></div>
    <h3 class="title"></h3>
    <a class="prev">‹</a>
    <a class="next">›</a>
    <a class="close">×</a>
    <a class="play-pause"></a>
    <ol class="indicator"></ol>
</div>

personal photos

building....

<div id="links">
    <a href="https://farm2.staticflickr.com/1632/25301731550_4c1ff67138_b.jpg" title="p1">
        <img src="https://farm2.staticflickr.com/1632/25301731550_4c1ff67138_t.jpg" alt="p1">
    </a>
    <a href="https://farm2.staticflickr.com/1451/25597328215_8ee0796595_b.jpg" title="p2">
        <img src="https://farm2.staticflickr.com/1451/25597328215_8ee0796595_t.jpg" alt="p2">
    </a>
    <a href="https://farm2.staticflickr.com/1511/24966860024_db391fe1cc_b.jpg" title="p3">
        <img scr="https://farm2.staticflickr.com/1511/24966860024_db391fe1cc_t.jpg" title="p3">
</div>

<div id="blueimp-gallery" class="blueimp-gallery blueimp-gallery-controls">
    <div class="slides"></div>
    <h3 class="title"></h3>
    <a class="prev">‹</a>
    <a class="next">›</a>
    <a class="close">×</a>
    <a class="play-pause"></a>
    <ol class="indicator"></ol>
</div>


<script src="../assets/js/blueimp-gallery.min.js"></script>

<script>
document.getElementById('links').onclick = function (event) {
    event = event || window.event;
    var target = event.target || event.srcElement,
        link = target.src ? target.parentNode : target,
        options = {index: link, event: event},
        links = this.getElementsByTagName('a');
    blueimp.Gallery(links, options);
};
</script>