---
title: "Memasang Lazy Loading pada Google Adsense"
url: /lazy-loading-google-adsense
pubDate: 2020-08-30T12:00:00+02:00
lastmod: 2020-08-30T12:00:00+02:00
draft: false
license: "MIT"
description: "Cara Memasang Lazy Loading Pada Google Adsense agar blog tidak lemot saat di muat."
tags: [Google Adsense, Blogger, Lazy Loading]
categories: [Homelab]
share:
  enable: true
  link: true
  twitter: true
  reddit: true
  bluesky: true
  hackernews: true
---

import { Image } from 'astro:assets';
import coverImg from '../../../assets/images/2026/automating-my-homelab-with-ansible/cover.webp';

<Image
  src={coverImg}
  alt="Automating My Homelab with Ansible"
  widths={[640, 960, 1280, 1600]}
  sizes="(max-width: 768px) 100vw, 900px"
  formats={['avif', 'webp']}
  quality={80}
  loading="lazy"
/>
Belajar: Memasang 4 Jenis Lazyload JavaScript Blogger

Pernahkah kamu mengunjungi sebuah blog yang kecepatannya lumayan cepat dari blog biasanya, kususnya blog yang bernaung di blogspot? Jika iya, maka tahukah kamu tema yang mereka gunakan biasanya adalah tema yang sudah di optimasi segi kecepatannya.

Seperti apa template blog yang sudah di optimasi itu? Jawabannya cukup simple, mereka hanya menggunakan sedikit tambahan JavaScript yang bernama " Lazy Load " yang mana peran dari lazyload ini adalah untuk menahan beban loading suatu objek.

## Apa itu Lazyload?
Banyak peranan penting dari yang namanya lazyload ini, namun kebanyakan lazyload hanya digunakan untuk mengoptimasi sebuah file gambar / foto yang berada disebuah blog.

Ada 3 fungsi yang bisa kita lakukan untuk menggunakan script Lazyload ini.
- Lazyload untuk memaksimalkan sebuah objek Foto | Gambar.
- Mengoptimasi bagian Video menggunakan lazyload.
- Lazyload kusus JavaScript, untuk menahan beban JavaScript / jQuery

Namun yang sering kita kenal, adalah lazyload untuk sebuah foto yang berguna membuat loading blog kita menjadi lebih ringan dan cepat daripada sebelumnnya.

### Keuntungan Mengunakan Lazyload
Menggunakan lazyload adalah saran terbaik yang dianjurkan oleh Google sendiri.

Sebab tidak ada cara lain yang terbaik untuk mendapatkan kecepatan situs selain memasang lazyload ini.

Dari segi keuntungan yang didapat jika memakai lazyload ini adalah sebagai berikut :

1. Mempercepat pemuatan halaman blog untuk segi gambar & video.
2. Memberikan nilai angka hijau disetiap alat cek kecepatan situs. 
3. Mendapatkan nilai tambahan dari sisi SEO.
4. Mengurangi masalah kehilangannya pengunjung situs.
5. Tampilan lebih dinamis dan segar.

Dipembahasan kali ini, mari kita pelajari bagaimana cara memasang lazyload kusus di blogspot. Jadi ini hanya berlaku buat pengguna blogger.com saja tidak berlaku bagi WordPress.

Sebab WordPress cukup memasang sebuah plugin maka otomatis lazyload akan berfungsi sendirinya.

Ada 4 cara yang saya bahas dalam tulisan ini, mulai dari segi yang paling mudah sampai tahap paling sulit.

Semua panduan ini saya buatkan dengan sepenuh hati dengan harapan membantu teman-teman semua dalam mengomptimalkan kecepatan loading blog yang di kelola.

### 4+ Memasang Lazyload di Blogger
Cara pertama adalah cara yang paling mudah dan simple yang saya jelaskan dibawah ini.

Lazyload JavaScript Otomatis
1. Salin / Copy kode JavaScript dibawah ini.
```/*! lazyload blogger v1.0.0 - Copyright (c) 2019 reedniv */
(function(a){a.fn.lazyload=function(b){var c={threshold:0,failurelimit:0,event:"scroll",effect:"show",container:window};if(b){a.extend(c,b)}var d=this;if("scroll"==c.event){a(c.container).bind("scroll",function(b){var e=0;d.each(function(){if(a.abovethetop(this,c)||a.leftofbegin(this,c)){}else if(!a.belowthefold(this,c)&&!a.rightoffold(this,c)){a(this).trigger("appear")}else{if(e++>c.failurelimit){return false}}});var f=a.grep(d,function(a){return!a.loaded});d=a(f)})}this.each(function(){var b=this;if(undefined==a(b).attr("original")){a(b).attr("original",a(b).attr("src"))}if("scroll"!=c.event||undefined==a(b).attr("src")||c.placeholder==a(b).attr("src")||a.abovethetop(b,c)||a.leftofbegin(b,c)||a.belowthefold(b,c)||a.rightoffold(b,c)){if(c.placeholder){a(b).attr("src",c.placeholder)}else{a(b).removeAttr("src")}b.loaded=false}else{b.loaded=true}a(b).one("appear",function(){if(!this.loaded){a("<img />").bind("load",function(){a(b).hide().attr("src",a(b).attr("original"))[c.effect](c.effectspeed);b.loaded=true}).attr("src",a(b).attr("original"))}});if("scroll"!=c.event){a(b).bind(c.event,function(c){if(!b.loaded){a(b).trigger("appear")}})}});a(c.container).trigger(c.event);return this};a.belowthefold=function(b,c){if(c.container===undefined||c.container===window){var d=a(window).height()+a(window).scrollTop()}else{var d=a(c.container).offset().top+a(c.container).height()}return d<=a(b).offset().top-c.threshold};a.rightoffold=function(b,c){if(c.container===undefined||c.container===window){var d=a(window).width()+a(window).scrollLeft()}else{var d=a(c.container).offset().left+a(c.container).width()}return d<=a(b).offset().left-c.threshold};a.abovethetop=function(b,c){if(c.container===undefined||c.container===window){var d=a(window).scrollTop()}else{var d=a(c.container).offset().top}return d>=a(b).offset().top+c.threshold+a(b).height()};a.leftofbegin=function(b,c){if(c.container===undefined||c.container===window){var d=a(window).scrollLeft()}else{var d=a(c.container).offset().left}return d>=a(b).offset().left+c.threshold+a(b).width()};a.extend(a.expr[":"],{"below-the-fold":"$.belowthefold(a, {threshold : 0, container: window})","above-the-fold":"!$.belowthefold(a, {threshold : 0, container: window})","right-of-fold":"$.rightoffold(a, {threshold : 0, container: window})","left-of-fold":"!$.rightoffold(a, {threshold : 0, container: window})"})})(jQuery);$(function(){$("img").lazyload({placeholder:"data:image/gif;base64,R0lGODlhAQABAIABAAAAAP///yH5BAEAAAEALAAAAAABAAEAAAICTAEAOw==",effect:"fadeIn",threshold:"-50"})});```
2. Buka Blogger > Template / Theme > Edit HTML > CTRL+F masukan tulisan " </body> " dikolom pencarian dan klik " ENTER "
3. Tempelkan / Paste kode JavaScript yang sudah disalin tadi, tepat dibagian atas kode </body>.
4. Klik " SIMPAN "

Lazyload akan otomatis berjalan tanpa harus kamu atur bagian-bagian tertentunya!
NB : Warna yang saya seleksi itu adalah gambar saat gambar terload di blog kamu, Jika kamu tidak menyukai akan tampilannya bisa ubah gambar dengan milik kamu sendiri

### Memasang Lazyload Manual
Cara kedua ini adalah cara sedikit sulit, Jika kamu tidak ingin rebit cukup melakukan cara pertama diatas saja.

Untuk cara kedua ini, lumayan sedikit susah bagi yang awam akan kode HTML. Sebab disini kamu harus menambahkan tagclass= disetiap bagian tag <img> dalam template.

Namun dengan menerapkan cara kedua ini, lebih efektif untuk menerapkan fungsi lazyload buat kecepatan blog kamu.

### JavaScript Lazyload Efek Scroll

1. Buka Blogger > Template / Theme > Edit HTML
2. Cari kode tag `<img> / <img =` setiap kode thumbanil template biasanya berbeda-beda, jadi bisa kamu cari yang tag `<img>` dengan berkaitan tulisan thumbanil.
```<img expr:alt='data:post.title' expr:title='data:post.title'expr:src='resizeImage(data:post.firstImageUrl, 225, "225:170")'/>```
3. Jika sudah ketemu dengan kode tag <img> thumbanil, langkah selanjutnya adalah merubah kode sebelumnya menjadi seperti dibawah ini.
4. Tambahkan tulisan class='lazy setiap tag <img class='lazy
5. Ubah kode tulisan exprc:src menjadi expr:data-src
6. Lagi tambahkan tulisan src dengan kode gambar ini  `data:image/png;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs=`
7. Kurang lebih kode lengkapnya seperti dikolom bawah ini.
```<img class='lazy' expr:alt='data:post.title' expr:title='data:post.title' expr:data-src='resizeImage(data:post.firstImageUrl, 225, "225:170")' src='data:image/png;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs='/>```
8.Apabila tag <img class=' sudah terisi sebelumnya, bisa kamu buat tulisan lazy di tag class yang sudah terisi dengan menekan spasi saja, Contohnya
`<img class='thumbanil lazy'`
9.0Langkah selanjutnya adalah menyalin kode JavaScript dibawah ini, dan meletakannya diatas kode </body>.
```<script type='text/javascript'>//<![CDATA[
function crotLazyLoad(){eval(function(p,a,c,k,e,d){e=function(c){return(c<a?'':e(parseInt(c/a)))+((c=c%a)>35?String.fromCharCode(c+29):c.toString(36))};if(!''.replace(/^/,String)){while(c--){d[e(c)]=k[c]||e(c)}k=[function(e){return d[e]}];e=function(){return'\\w+'};c=1};while(c--){if(k[c]){p=p.replace(new RegExp('\\b'+e(c)+'\\b','g'),k[c])}}return p}('u B(){Y(v e=o.1r("B"),t=0;t<e.1q;t++)Q(e[t])&&(e[t].N=e[t].1p("1n-N"))}u Q(e){v t=e.1t();Z t.1x>=0&&t.1w>=0&&t.1v<=(y.1u||o.T.1m)&&t.1k<=(y.1c||o.T.1b)}v b=["\\r\\m\\m\\D\\G\\a\\f\\c\\M\\n\\p\\c\\a\\f\\a\\k","\\h\\f","\\r\\c\\c\\r\\l\\A\\D\\G\\a\\f\\c","\\g\\h\\r\\m","\\p\\l\\k\\h\\g\\g","\\V\\1a\\1e\\R\\h\\f\\c\\a\\f\\c\\M\\h\\r\\m\\a\\m","\\w\\p\\a\\1l\\p\\c\\k\\n\\l\\c","\\r","\\1f\\w\\a\\k\\L\\1j\\a\\g\\a\\l\\c\\h\\k\\W\\g\\g","\\g\\a\\f\\q\\c\\A","\\w\\p\\a\\k\\W\\q\\a\\f\\c","\\c\\a\\p\\c","\\m\\h\\l\\w\\F\\a\\f\\c\\D\\g\\a\\F\\a\\f\\c","\\1i\\h\\m\\L","\\l\\g\\n\\l\\1g","\\p\\l\\k\\h\\g\\g\\1h\\h\\J","\\c\\h\\J","\\q\\a\\c\\S\\h\\w\\f\\m\\n\\f\\q\\R\\g\\n\\a\\f\\c\\1z\\a\\l\\c","\\A\\k\\a\\X","\\a\\1y\\a\\l","\\q\\a\\c\\D\\g\\a\\F\\a\\f\\c\\S\\L\\1F\\m","\\p\\l\\k\\h\\g\\g\\U\\a\\n\\q\\A\\c","\\n\\f\\f\\a\\k\\U\\a\\n\\q\\A\\c","\\J\\k\\a\\G\\a\\f\\c\\V\\a\\X\\r\\w\\g\\c","\\n\\c\\a\\F"];u I(d,j){y[b[0]]?y[b[0]](d,j):y[b[2]](b[1]+d,j)}I(b[3],B),I(b[4],B),o[b[0]](b[5],u(){b[6];Y(v d=o[b[8]](b[7]),j=d[b[9]],s=/1D|1B/i[b[11]](1G[b[10]])?o[b[12]]:o[b[13]],C=u(d,j,s,C){Z(d/=C/2)<1?s/2*d*d*d+j:s/2*((d-=2)*d*d+2)+j};j--;){d[b[1C]](j)[b[0]](b[14],u(d){v j,E=s[b[15]],x=o[b[1A]](/[^#]+$/[b[19]](1H[b[18]])[0])[b[17]]()[b[16]],z=s[b[1d]]-y[b[1s]],O=z>E+x?x:z-E,K=1o,H=u(d){j=j||d;v x=d-j,z=C(x,E,O,K);s[b[15]]=z,K>x&&P(H)};P(H),d[b[1E]]()})}});',62,106,'||||||||||x65|_0x1b5d|x74|_0xdd48x2||x6E|x6C|x6F||_0xdd48x3|x72|x63|x64|x69|document|x73|x67|x61|_0xdd48x4||function|var|x75|_0xdd48x7|window|_0xdd48x8|x68|lazy|_0xdd48x5|x45|_0xdd48x6|x6D|x76|_0xdd48xb|registerListener|x70|_0xdd48xa|x79|x4C|src|_0xdd48x9|requestAnimationFrame|isInViewport|x43|x42|documentElement|x48|x44|x41|x66|for|return|||||||||||x4F|clientWidth|innerWidth|21|x4D|x71|x6B|x54|x62|x53|left|x20|clientHeight|data|900|getAttribute|length|getElementsByClassName|22|getBoundingClientRect|innerHeight|top|right|bottom|x78|x52|20|trident|24|firefox|23|x49|navigator|this'.split('|'),0,{}));} eval(function(p,a,c,k,e,d){e=function(c){return c.toString(36)};if(!''.replace(/^/,String)){while(c--){d[c.toString(a)]=k[c]||c.toString(a)}k=[function(e){return d[e]}];e=function(){return'\\w+'};c=1};while(c--){if(k[c]){p=p.replace(new RegExp('\\b'+e(c)+'\\b','g'),k[c])}}return p}('j 4=["\\7\\9\\9\\e\\d\\a\\b\\8\\i\\g\\h\\8\\a\\b\\a\\k","\\f\\c\\7\\9","\\7\\8\\8\\7\\m\\l\\e\\d\\a\\b\\8","\\c\\b\\f\\c\\7\\9"];5[4[0]]?5[4[0]](4[1],6,!1):5[4[2]]?5[4[2]](4[1],6):5[4[3]]=6;5[4[0]]?5[4[0]](4[1],6,!1):5[4[2]]?5[4[2]](4[1],6):5[4[3]]=6;',23,23,'||||_0xdfb4|window|crotLazyLoad|x61|x74|x64|x65|x6E|x6F|x76|x45|x6C|x69|x73|x4C|var|x72|x68|x63'.split('|'),0,{}));
//]]></script>```
10. Klik " SIMPAN " Template.

NB: Setiap tag <img> bisa kamu tambahkan class='lazy', jadi bukan hanya tag <img> thumbanil saja.

### JavaScript Lazyload Menggunakan CSS

1. Silahkan salin kode jQuery dibawah ini.
```<script type='text/javascript'>//<![CDATA[
$('img').each(function(){var url = $(this).attr('data-src');$(this).attr('src',url);$(this).removeAttr('data-src')});$('.lazy-load').each(function(){var url = $(this).attr('data-src');$(this).attr('style','background-image:url("'+url+'");');$(this).removeAttr('data-src');$(this).removeClass('lazy-load')});
//]]></script>```

Catatan: Pastikan didalam template kamu sudah terpasang jQuery versi berapapun.

2. Salin lagi kode CSS dikolom bawah ini.
```<style>.lazy-load {position: relative;display: block;background-color: #f5f6f7;
    width: 100%;
    height: 100%;
    background-size: cover;
    background-position: center center;
    background-repeat: no-repeat;
    z-index: 1;}
</style>```
3. Letakan kode yang disalin tadi di atas </head> | </body>
4. Langkah berikutnya adalah mengedit bagian HTML template, cari kode dengan CTRL+F <b:includable id='postFeaturedImage' var='post'> ini dalam template, bisa disesuaikan dengan kode thumbnail template kamu masing-masing.
5. Kurang lebih nanti kodenya seperti contoh milik saya dibawah ini.
```<div class='post-image-wrap item_image'>
                <a class='post-image-link' expr:href='data:post.url'>
                   <b:if cond='data:post.featuredImage'>
                    <img class='lazy-load post-thumb' expr:alt='data:post.title' expr:data-src='data:post.featuredImage resizeImage 300'/>
                    <b:else/>
                    <img class='lazy-load post-thumb' data-src='https://4.bp.blogspot.com/-O3EpVMWcoKw/WxY6-6I4--I/AAAAAAAAB2s/KzC0FqUQtkMdw7VzT6oOR_8vbZO6EJc-ACK4BGAYYCw/w680/nth.png' expr:alt='data:post.title'/>
                  </b:if>
                </a>
              </div>```
6. Silahkan tambahkan kode lazy-load dibagian `<img class='` dan juga bagian kode src dengan menambahkan `text data-` menjadi `data-src`
7. Ubah kode <img menjadi <span | kode langkapnya `<span class='lazy-load post-thumb' expr:alt='data:post.title' expr:data-src='data:post.featuredImage resizeImage 300'/>`
8. Jika sudah, Klik SIMPAN

Kode HTML thumbnail diatas, saya ambil dari kode terbaru template blogger, akan terlihat berbeda jika template yang kamu gunakan masih versi lama.

### jQuery Lazyload Scroll Menggunakan CSS
Cara ini kurang lebih sama halnya seperti cara nomor tiga menggunakan CSS, Hanya beda dibagian kode JavaScript saja.

1. Salin kode JavaScript dibawah ini.

```<script>
//<![CDATA[
!function(b){$(".lazyload").each(function(){var e=b(this),f=e.attr("data-image"),g=Math.round(e.width()),h=Math.round(e.height()),a="w"+g+"-h"+h+"-p-k-no-nu",c="";if(f.match("/s72-c")){c=f.replace("/s72-c","/"+a)}else{if(f.match("/w72-h")){c=f.replace("/w72-h72-p-k-no-nu","/"+a)}else{if(f.match("=w72-h")){c=f.replace("=w72-h72-p-k-no-nu","="+a)}else{c=f}}}b(window).on("load resize scroll",d);function d(){var k=b(window).height(),i=b(window).scrollTop(),j=e.offset().top;if(i+k>j){var l=new Image();l.onload=function(){e.attr("style","background-image:url("+this.src+")").addClass("show-hjn")},l.src=c}}d()})}(jQuery);
//]]>
</script>```
2. Salin lagi kode CSS dikolom bawah ini.

```<style>
.post-thumb {position: relative;display: block;
    background-color: #f5f6f7;
    width: 100%;
    height: 100%;
    background-size: cover;
    background-position: center center;
    background-repeat: no-repeat;
    z-index: 1;
    opacity: 0;
    transition: opacity .35s ease;}
.post-thumb.lazyload {opacity:1}
</style>```

3. Letakan kedua kode jQuery & CSS yang disalin tadi diatas kode </head>
4. Masih dalam mode edit HTML template, cari kode HTML thumbnail <img class='
5. Jika ketemu ganti `<img class='' dengan kode `<span class='post-thumb lazyload'` dan `expr:src` ganti menjadi `expr:data-image` lalu kolomnya isi dengan  `resizeImage(data:post.featuredImage, 72, &quot;1:1&quot;)`
`<span class='post-thumb lazyload' expr:alt='data:post.title' expr:src='resizeImage(data:post.featuredImage, 72, &quot;1:1&quot;)'/>`
6. Selanjutnya klik SIMPAN | SAVE

### Bonus Lazyload Scroll Google AdSense
Tidak banyak yang perlu kamu lakukan, cukup salin kode JavaScript dibawah ini.
```<script>
// Lazy Load AdSense
var lazyadsense=!1;window.addEventListener("scroll",function(){(0!=document.documentElement.scrollTop&&!1===lazyadsense||0!=document.body.scrollTop&&!1===lazyadsense)&&(!function(){var e=document.createElement("script");e.type="text/javascript",e.async=!0,e.src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js";var a=document.getElementsByTagName("script")[0];a.parentNode.insertBefore(e,a)}(),lazyadsense=!0)},!0);
//]]></script>```

Letakan diatas </head> dan klik SIMPAN

Selanjutnya silahkan kamu cek berbagai tool online untuk cek kecepatan loading blog.
- GTMetrix - Rekomedasi
- Google PageSpeed
- Pingdom

Masih kurang dengan panduan diatas? Silahkan tulis dikolom komentar tentang pengoptimalan kecepatan bagian apa lagi yang di inginkan.

Yang nantinya sebisa mungkin admin bantu untuk merangkumnya.

## Akhir Kata
Jika ada pertanyaan atau juga ada bagian belum di mengerti, jangan ragu untuk menulis pertanyaan dikolom komentar blog ini, yang nantinya akan saya bantu menjawabnya.
