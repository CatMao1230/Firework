# Firework
<h1><img class="alignnone  wp-image-99" src="https://catmaoblog.files.wordpress.com/2016/10/6lqz4de.png" alt="Icon made by Freepik from www.flaticon.com" width="40" height="40" /> <a href="https://catmao1230.github.io/Firework/" target="_blank">點我前往</a></h1>
<h1><img class="alignnone  wp-image-99" src="https://catmaoblog.files.wordpress.com/2016/10/6lqz4de.png" alt="Icon made by Freepik from www.flaticon.com" width="40" height="40" /> <a href="https://catmaoblog.wordpress.com/2016/10/31/firework/" target="_blank">WordPress</a></h1>
<h1><img class="alignnone  wp-image-41" src="https://catmaoblog.files.wordpress.com/2016/10/3h9rzur.png" alt="Icon made by Popcorns Arts from www.flaticon.com" width="40" height="40" /> 前言</h1>
透過這次製作煙火，我學會了如何使用 Javascript 的 Object ，也活用了陣列與 Timer ，這裡的煙火物理現象並不符合實際的物理現象，因為我物理不太好，不過乍看之下還是有幾分像，準確的物理現象並不在這次的探討範圍內。
<h1><img class="alignnone  wp-image-43" src="https://catmaoblog.files.wordpress.com/2016/10/ril6i6c.png" alt="Icon made by flaticon from www.flaticon.com" width="40" height="40" /> 程式碼</h1>
<ol>
	<li> Fireworks 裡是用來存放 Firework 的陣列，而 FirstDots 是用來存放第一個點的陣列，每次點擊畫面都會施放煙火，煙火會先以一個小點往上， 1.5 秒後此點消失，而煙火則出現。</li>
	<li> Firework 和 Ball 都是 Object ，Firework 裡的 Create() 是用來產生一堆新的 Ball 並放進 Firework 裡的 Balls 陣列。</li>
	<li>Object 的教學可以參考 <a href="https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Guide/Working_with_Objects">JavaScript | MDN</a> ，我這次使用的方法如下：
<pre><code>function Dot(x, y){ // 宣告 Object 名稱，可以給值
    this.x = x;
    this.y = y;
    this.r = 1;

    this.Show = function(){ // Object 除了變數也可以有函式
        // ..
    }
}
</code></pre>
</li>
	<li>宣告 Object 以後，就可以動態產生新的物件，
<pre>var dot = new Dot(10, 10);</pre>
也可以直接 push 到陣列裡。
<pre>Dots.push(new Dot(10, 10));</pre>
陣列使用的方法可以參考 <a href="http://sweeteason.pixnet.net/blog/post/41263148-javascript-%E5%B8%B8%E7%94%A8%E7%9A%84%E9%99%A3%E5%88%97(array)%E6%93%8D%E4%BD%9C%E5%A4%A7%E5%85%A8" target="_blank">Javascript 常用的陣列(Array)操作大全</a>，裡面的解說都很詳盡，這次程式碼有用到的是 push 和 shift ，shift 是將陣列第一個刪除，後面都往前挪的方法。</li>
	<li>煙火會隨時間消失，我用了兩種 Timer 來控制，第一個是 <a href="http://www.w3schools.com/jsref/met_win_settimeout.asp">setTimeout()</a> ，第二個是 <a href="http://www.w3schools.com/jsref/met_win_setinterval.asp">setInterval()</a> ，兩種差異在於： setTimeout 是幾秒後會執行函式一次， setInterval 是過幾秒就執行函式，所以前者只會執行一次，後者會執行很多次，可以利用 clearInterval() 來關閉 setInterval 的 Timer 。</li>
	<li>我畫上煙火的每個點是要一直重複執行的，所以就需要用到 setInterval ，而第一個點往上升之後消失產生煙火則是只會觸發一次，所以使用 setTimeout ，兩種 Timer 的使用時機是不一樣的。</li>
</ol>
<h1><img class="alignnone  wp-image-42" src="https://catmaoblog.files.wordpress.com/2016/10/tpodion.png" alt="tpodion" width="40" height="40" /> 圖片素材</h1>
<ul class="alt">
	<li><a href="http://www.freepik.com/free-vector/beautiful-constellations-background_844910.htm" target="_blank">Designed by Freepik</a></li>
</ul>
<h1><img class="alignnone  wp-image-42" src="https://catmaoblog.files.wordpress.com/2016/10/tpodion.png" alt="tpodion" width="40" height="40" /> 參考資料</h1>
<ul class="alt">
	<li><a href="https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Guide/Working_with_Objects" target="_blank">物件的使用 / MDN</a></li>
	<li><a href="http://sweeteason.pixnet.net/blog/post/41263148-javascript-%E5%B8%B8%E7%94%A8%E7%9A%84%E9%99%A3%E5%88%97(array)%E6%93%8D%E4%BD%9C%E5%A4%A7%E5%85%A8" target="_blank">Javascript 常用的陣列(Array)操作大全 / 小雕雕的家</a></li>
</ul>
