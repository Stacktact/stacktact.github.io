---
permalink: "/eriks_hats"
layout: single
author_profile: true
layout: null

title: "Sorting Erik's Hats: Very Important"
hats:
  - hat_01:
    name: hat_01
    color: 4
    poofyness: 3
    height: 3
    fabulousness: 2
  - hat_02:
    name: hat_02
    color: 2
    poofyness: 8
    height: 5
    fabulousness: 5
  - hat_03:
    name: hat_03
    color: 5
    poofyness: 2
    height: 2
    fabulousness: 1
  - hat_04:
    name: hat_04
    color: 3
    poofyness: 7
    height: 4
    fabulousness: 7
  - hat_05:
    name: hat_05
    color: 9
    poofyness: 9
    height: 9
    fabulousness: 4
  - hat_06:
    name: hat_06
    color: 1
    poofyness: 4
    height: 7
    fabulousness: 5
  - hat_07:
    name: hat_07
    color: 6
    poofyness: 6
    height: 6
    fabulousness: 6
  - hat_08:
    name: hat_08
    color: 9
    poofyness: 1
    height: 1
    fabulousness: 9
  - hat_09:
    name: hat_09
    color: 8
    poofyness: 5
    height: 8
    fabulousness: 8
---

<div class="wrapper">
  <h2>{{page.title}}</h2>

  <div id="sorts" class="button-group">
    <button class="button is-checked" data-sort-by="original-order">original</button>
    <button class="button" data-sort-by="hatcolor">color</button>
    <button class="button" data-sort-by="poofyness">poofyness</button>
    <button class="button" data-sort-by="hatheight">height</button>
    <button class="button" data-sort-by="fabulousness">fabulousness</button>
    <button class="button" data-sort-by="random">random</button>
  </div>

  <div class="grid cf">
    {% for hat in page.hats %}
      <div class="grid-item">
        <img src="/images/eriks_hats/{{hat.name}}.png" />
        <span>color: </span>
        <span class="hatcolor">{{hat.color}}</span>
        <span>poofyness: </span>
        <span class="poofyness">{{hat.poofyness}}</span>
        <span>hat height: </span>
        <span class="hatheight">{{hat.height}}</span>
        <span>fabulousness: </span>
        <span class="fabulousness">{{hat.fabulousness}}</span>
      </div>
    {% endfor %}
  </div>
</div>

<script src="http://cdnjs.cloudflare.com/ajax/libs/jquery/2.2.2/jquery.min.js" type="text/javascript"></script>
<script src="https://npmcdn.com/isotope-layout@3/dist/isotope.pkgd.js"></script>
<script src="http://npmcdn.com/imagesloaded@4/imagesloaded.pkgd.js" type="text/javascript"></script>

<script>
  // http://isotope.metafizzy.co/

  $( document ).ready(function() {
    var $grid = $('.grid').imagesLoaded( function() {
      $('.grid').isotope({
        itemSelector: '.grid-item',
        layoutMode: 'fitRows',
        getSortData: {
          hatcolor: '.hatcolor parseInt',
          poofyness: '.poofyness parseInt',
          hatheight: '.hatheight parseInt',
          fabulousness: '.fabulousness parseInt'
        }
      });
    });

    // bind sort button click
    $('#sorts').on( 'click', 'button', function() {
      var sortByValue = $(this).attr('data-sort-by');
      console.log(sortByValue);
      $grid.isotope({ sortBy: sortByValue });
    });

    // change is-checked class on buttons
    $('.button-group').each( function( i, buttonGroup ) {
      var $buttonGroup = $( buttonGroup );
      $buttonGroup.on( 'click', 'button', function() {
        $buttonGroup.find('.is-checked').removeClass('is-checked');
        $( this ).addClass('is-checked');
      });
    });

    $grid.on( 'arrangeComplete', function(event, filteredItems) {
      console.log($(filteredItems));
    });
  });
</script>

<style>
* { box-sizing: border-box; }

body {
  font-family: sans-serif;
  padding: 0;
  margin: 0 auto; 
}

.wrapper {
  width: 100%;
  margin: 40px 0 0 40px; 
}

/* ---- button ---- */

.button {
  display: inline-block;
  padding: 0.5em 1.0em;
  background: #EEE;
  border: none;
  border-radius: 7px;
  background-image: linear-gradient( to bottom, hsla(0, 0%, 0%, 0), hsla(0, 0%, 0%, 0.2) );
  color: #222;
  font-family: sans-serif;
  font-size: 16px;
  text-shadow: 0 1px white;
  cursor: pointer;
}

.button:hover {
  background-color: #8CF;
  text-shadow: 0 1px hsla(0, 0%, 100%, 0.5);
  color: #222;
}

.button:active,
.button.is-checked {
  background-color: #28F;
}

.button.is-checked {
  color: white;
  text-shadow: 0 -1px hsla(0, 0%, 0%, 0.8);
}

.button:active {
  box-shadow: inset 0 1px 10px hsla(0, 0%, 0%, 0.8);
}

/* ---- button-group ---- */

.button-group {
  margin-bottom: 20px;
}

.button-group:after {
  content: '';
  display: block;
  clear: both;
}

.button-group .button {
  float: left;
  border-radius: 0;
  margin-left: 0;
  margin-right: 1px;
}

.button-group .button:first-child { border-radius: 0.5em 0 0 0.5em; }
.button-group .button:last-child { border-radius: 0 0.5em 0.5em 0; }

/* ---- isotope ---- */

.grid {
  border: 1px solid #333;
  width: 970px;
}

/* clear fix */
.grid:after {
  content: '';
  display: block;
  clear: both;
}

/* ---- .grid-item ---- */

.grid-item {
  position: relative;
  float: left;
  width: 300px;
  margin: 10px;
  padding: 0;
  background: #888;
  color: #262524;
}

.grid-item img {
  width: 300px;
  height: 300px;
}

.grid-item > * {
  margin: 0;
  padding: 0;
}

.grid-item span {
  display: none;
}
</style>
