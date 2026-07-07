---
layout: archive
title: "Photography"
permalink: /photography/
author_profile: true
---

<div class="av-gallery">
  <a class="av-shot" href="/images/IMG_20221103_224909_564.jpg"><img src="/images/IMG_20221103_224909_564.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/IMG_20230110_230738_245.jpg"><img src="/images/IMG_20230110_230738_245.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/IMG_20230110_230738_337.jpg"><img src="/images/IMG_20230110_230738_337.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/IMG_20230116_033855_216.jpg"><img src="/images/IMG_20230116_033855_216.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/IMG_20230116_033855_302.jpg"><img src="/images/IMG_20230116_033855_302.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/IMG_20230611_172952_436.jpg"><img src="/images/IMG_20230611_172952_436.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/DSC08530.jpg"><img src="/images/DSC08530.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/DSC08081-2.jpg"><img src="/images/DSC08081-2.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/DSC08435.jpg"><img src="/images/DSC08435.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/DSC08594.jpg"><img src="/images/DSC08594.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/DSC08588.jpg"><img src="/images/DSC08588.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/DSC07869.jpg"><img src="/images/DSC07869.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/DSC07702.jpg"><img src="/images/DSC07702.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/DSC07760.jpg"><img src="/images/DSC07760.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
  <a class="av-shot" href="/images/DSC07792.jpg"><img src="/images/DSC07792.jpg" loading="lazy" alt="Photograph by Apurv Varshney"></a>
</div>

<script>
(function(){
  var shots = Array.prototype.slice.call(document.querySelectorAll('.av-shot'));
  if(!shots.length) return;
  var srcs = shots.map(function(a){ return a.getAttribute('href'); });
  var i = 0;

  var lb = document.createElement('div');
  lb.className = 'av-lb';
  lb.innerHTML =
      '<button class="av-lb__btn av-lb__close" aria-label="Close">&times;</button>'
    + '<button class="av-lb__btn av-lb__prev" aria-label="Previous">&#8249;</button>'
    + '<img alt="">'
    + '<button class="av-lb__btn av-lb__next" aria-label="Next">&#8250;</button>'
    + '<div class="av-lb__count"></div>';
  document.body.appendChild(lb);

  var img = lb.querySelector('img');
  var count = lb.querySelector('.av-lb__count');

  function show(n){ i = (n + srcs.length) % srcs.length; img.src = srcs[i]; count.textContent = (i+1) + ' / ' + srcs.length; }
  function open(n){ show(n); lb.classList.add('is-open'); document.body.style.overflow = 'hidden'; }
  function close(){ lb.classList.remove('is-open'); document.body.style.overflow = ''; img.src = ''; }

  shots.forEach(function(a, n){ a.addEventListener('click', function(e){ e.preventDefault(); open(n); }); });
  lb.querySelector('.av-lb__close').addEventListener('click', close);
  lb.querySelector('.av-lb__prev').addEventListener('click', function(e){ e.stopPropagation(); show(i-1); });
  lb.querySelector('.av-lb__next').addEventListener('click', function(e){ e.stopPropagation(); show(i+1); });
  lb.addEventListener('click', function(e){ if(e.target === lb) close(); });
  document.addEventListener('keydown', function(e){
    if(!lb.classList.contains('is-open')) return;
    if(e.key === 'Escape') close();
    else if(e.key === 'ArrowLeft')  show(i-1);
    else if(e.key === 'ArrowRight') show(i+1);
  });
})();
</script>