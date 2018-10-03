<!DOCTYPE html>
<html>
<head>
  <!-- <meta http-equiv="content-type" content="text/html; charset=UTF-8" /> -->
  <title>Google Maps Multiple Markers</title>

          <style>
            /* Always set the map height explicitly to define the size of the div
             * element that contains the map. */

            #map {
              height:  800px;;
            }
            /* Optional: Makes the sample page fill the window. */
        html, body {
             height: 100%;
              margin: 0;
              padding: 0;
            }
          </style>
</head>
<body>
  <div id="map" style="width: 100%; height: 100%;"></div>
  <script
   src="https://maps.googleapis.com/maps/api/js?key=AIzaSyBOzaUf2r0-JbOk211V3IAWtda1-g5SemA&callback"
          type="text/javascript"></script>
  <script >

      var locations = [
//===============france============================
      ['<div id="bodyContent">'+
        '<p><b>Sens Unique </b>'+
      ' 13 Rue du Roi de Sicile, 75004 Paris '+
     '<a href="https://sensuniqueparis.com/presentation-de-la-marque-sous-le-manteau/">-website</a></p>', 48.856095, 2.358783, 4],

      ['<div id="bodyContent">'+
      '<p><b>Printemps </b>'+
      '64 Boulevard Haussmann, 75009 Paris, France ' +
     '<a href="https://beaute-printemps.placedestendances.com/fr/fr/parfum">-website</a></p>', 48.873909, 2.328658, 5],

      [  '<div id="bodyContent">'+
        '<p><b>Cour des Hommes </b>'+
      '11 Rue des Clercs, 57000 Metz, France ' +
     '<a href="http://lacourdeshommes.com/">-website</a></p>',  49.117584, 6.174013, 3],


     ['<div id="bodyContent">'+
       '<p><b>slm Lab </b>'+
     '24 Rue Berthe,75018 Paris </p>', 48.885626, 2.339826, 2],
//===============Skins===============================

      ['<div id="bodyContent">'+
        '<p><b>Skins: Amsterdam Centre </b>'+
      'Runstraat 11, 1016 GJ Amsterdam </p>' +
      '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a>',  52.368793, 4.883678, 1],

      ['<div id="bodyContent">'+
        '<p><b>Skins: Amsterdam South </b>' +
      'Van Baerlestraat 27, 1071 AN Amsterdam' +
       '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a></p>', 52.358631, 4.878624, 2],

      [  '<div id="bodyContent">'+
        '<p><b>Skins: Breda </b>'+
       'Breda Ginnekenweg 31, 4818 JA Breda' +
       '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a></p>', 51.573349, 4.783166, 2],

      [  '<div id="bodyContent">'+
        '<p><b>Skins: Den Haag </b>'+
      'Wagenstraat 32, 2512 AX Den Haag' +
       '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a></p>', 52.205641, 5.959745, 2],

      [  '<div id="bodyContent">'+
        '<p><b>Skins: Eindhoven </b>'+
      'Hooghuisstraat 33, 5611 GS Eindhoven' +
       '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a></p>', 51.437609, 5.477353, 2],

      [  '<div id="bodyContent">'+
        '<p><b>Skins: Groningen </b>'+
      'Oude Boteringestraat 12, 9712 GH Groningen' +
       '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a></p>', 53.218943,  6.564621, 2],

      [  '<div id="bodyContent">'+
        '<p><b>Skins: Laren </b>'+
      'Laren Naarderstraat 15A, 1251 AX Laren' +
       '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a></p>', 52.258074, 5.223326, 2],

      ['<div id="bodyContent">'+
        '<p><b>Skins: Oisterwijk </b>'+
      'De Lind 13, 5061 HS Oisterwijk' +
       '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a></p>', 51.580861, 5.195261, 2],

      [    '<div id="bodyContent">'+
        '<p><b>Skins: Oosterbeek </b>'+
      'Utrechtseweg 190, 6862 AW Oosterbeek' +
       '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a></p>', 51.987509, 5.840029, 2],

      [  '<div id="bodyContent">'+
      '<p><b>Skins: Rotterdam </b>'+
      'Kruiskade 75-77, 3012 EE Rotterdam' +
       '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a></p>', 51.92235,4.474311, 2],

      [ '<div id="bodyContent">'+
        '<p><b>Skins: Gent </b>'+
      'Korenmarkt 16- ‘Oude Postkantoor’, 9000 Gent' +
       '<a href="https://www.skins.nl/en/brands/sous-le-manteau">-website</a></p>',51.05428 ,3.721162 , 2],
//=================Russia===============
      [ '<div id="bodyContent">'+
        '<p><b>Aromateka </b>'+
      'Znamenka Ulitsa, 7/3, Пушкино, Moskovskaya oblast, Russia, 119019' +
       '<a href="https://aroma-teka.ru/en/">-website</a></p>',55.749283 , 37.607453 , 2],

      [  '<div id="bodyContent">'+
        '<p><b>Eiffel </b>'+
      'Ulitsa Kuybysheva, 26, Vladikavkaz, Северная Осетия-Алания республика' +
       '<a href="https://www.officinadelleessenze.com/en/retailer/eiffel-2/">-website</a></p>',55.749283 , 37.607453 , 2],

      [ '<div id="bodyContent">'+
        '<p><b>Lukse </b>'+
      'Serebrennikovskaya Ulitsa, 31, Novosibirsk, Novosibirskaya oblast' +
       '<a href="https://lukse.ru/">-website</a></p>',55.026864 , 82.925049 , 2],

      [ '<div id="bodyContent">'+
        '<p><b>Giorgio </b>'+
      '18-1 A Uchitel skaya st.,St. Petersburg' +
       '<a href="http://fragrancerussia.com/en/shops/giorgio-krasnodar">-website</a></p>',59.93428 , 30.335099 , 2],
//=================Middle East===================
      [ '<div id="bodyContent">'+
        '<p><b>Perfume Bay: Al Ain </b>'+
      'Abu Dhabi - United Arab Emirates' +
       '<a href="https://www.perfumebays.com/">-website</a></p>', 24.159075 , 55.808119 , 2],

      [ '<div id="bodyContent">'+
        '<p><b>Perfume Bay: Abu Dhabi </b>'+
      'Marina Mall Luxury Section - Abu Dhabi' +
       '<a href="https://www.perfumebays.com/">-website</a></p>', 24.477385 , 54.320757 , 2],

      [ '<div id="bodyContent">'+
        '<p><b>Omar </b>'+
      'Muscat Oman' +
       '<a href="Omar, Muscat Oman">-website</a></p>', 23.580222 , 58.564049 , 2],

      [ '<div id="bodyContent">'+
        '<p><b>L’Odore </b>'+
      'Eastern Ring Rd, Ash Shuhada, Riyadh 12486, Saudi Arabia' +
       '<a href="https://lodore.com/index.php?route=product/manufacturer/info&manufacturer_id=35">-website</a></p>', 24.780971 , 46.731373 , 2],
//==================USA====================
      [ '<div id="bodyContent">'+
        '<p><b>Maison10 </b>'+
      '260 5th Ave 2nd floor, New York, NY 10001' +
       '<a href="https://www.maison10.com/">-website</a></p>', 40.745094 , -73.987143 , 2],

      [  '<div id="bodyContent">'+
        '<p><b>Space 240 </b>'+
      '240 East 29th st, New York'
      , 40.741717 , -73.978676 , 2],
//==================spain====================
      [  '<div id="bodyContent">'+
        '<p><b>The Perfumery </b>'+
      'Carrer de Sant Pere Mes Alt, 58 08003 Barcelona' +
       '<a href="https://www.theperfumerybarcelona.com/en/">-website</a></p>', 41.388842  , 2.17747 , 2],
//==================switzerland==================
      [ '<div id="bodyContent">'+
        '<p><b>Zurich </b>'+
      'Spitzenhaus : Börsenstrasse 14, 8001 Zürich ' +
       '<a href="https://www.spitzenhaus.com/en">-website</a></p>',  47.368124, 8.540685 , 2],
//===================German==================
      [  '<div id="bodyContent">'+
        '<p><b>Schnitzler </b>'+
      '11 Schadow-Arkaden, 40212 Duesseldorf' +
       '<a href="https://www.parfuemerie-schnitzler.de/filialen/schadow-arkaden/">-website</a></p>', 51.225433 , 6.780477 , 2],

      [  '<div id="bodyContent">'+
        '<p><b>Parfuemerie </b>'+
       'Jungfernstieg 26 – 28 , 20354 Hambourg' +
       '<a href="https://www.parfuemerie-pieper.de/">-website</a></p>',  53.553721 , 9.990426 , 2],


      [  '<div id="bodyContent">'+
        '<p><b>Parfums Uniques </b>'+
      'Klenzestrasse 22 (at Gärtnerplatz) , 80469 Munich' +
       '<a href="http://www.parfums-uniques.de/sillage-philosophy/">-website</a></p>', 48.132303 , 11.576714 , 2],

    ];

    var map = new google.maps.Map(document.getElementById('map'), {
      zoom: 2 ,
      center: new google.maps.LatLng( 48.3794 ,31.1656),

      styles:[
  {
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#212121"
      }
    ]
  },
  {
    "elementType": "labels.icon",
    "stylers": [
      {
        "visibility": "off"
      }
    ]
  },
  {
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#757575"
      }
    ]
  },
  {
    "elementType": "labels.text.stroke",
    "stylers": [
      {
        "color": "#212121"
      }
    ]
  },
  {
    "featureType": "administrative",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#757575"
      }
    ]
  },
  {
    "featureType": "administrative.country",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#9e9e9e"
      }
    ]
  },
  {
    "featureType": "administrative.land_parcel",
    "stylers": [
      {
        "visibility": "off"
      }
    ]
  },
  {
    "featureType": "administrative.locality",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#bdbdbd"
      }
    ]
  },
  {
    "featureType": "administrative.neighborhood",
    "stylers": [
      {
        "visibility": "off"
      }
    ]
  },
  {
    "featureType": "poi",
    "elementType": "labels.text",
    "stylers": [
      {
        "visibility": "off"
      }
    ]
  },
  {
    "featureType": "poi",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#757575"
      }
    ]
  },
  {
    "featureType": "poi.business",
    "stylers": [
      {
        "visibility": "off"
      }
    ]
  },
  {
    "featureType": "poi.park",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#181818"
      }
    ]
  },
  {
    "featureType": "poi.park",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#616161"
      }
    ]
  },
  {
    "featureType": "poi.park",
    "elementType": "labels.text.stroke",
    "stylers": [
      {
        "color": "#1b1b1b"
      }
    ]
  },
  {
    "featureType": "road",
    "stylers": [
      {
        "visibility": "off"
      }
    ]
  },
  {
    "featureType": "road",
    "elementType": "geometry.fill",
    "stylers": [
      {
        "color": "#2c2c2c"
      }
    ]
  },
  {
    "featureType": "road",
    "elementType": "labels",
    "stylers": [
      {
        "visibility": "off"
      }
    ]
  },
  {
    "featureType": "road",
    "elementType": "labels.icon",
    "stylers": [
      {
        "visibility": "off"
      }
    ]
  },
  {
    "featureType": "road",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#8a8a8a"
      }
    ]
  },
  {
    "featureType": "road.arterial",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#373737"
      }
    ]
  },
  {
    "featureType": "road.highway",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#3c3c3c"
      }
    ]
  },
  {
    "featureType": "road.highway.controlled_access",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#4e4e4e"
      }
    ]
  },
  {
    "featureType": "road.local",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#616161"
      }
    ]
  },
  {
    "featureType": "transit",
    "stylers": [
      {
        "visibility": "off"
      }
    ]
  },
  {
    "featureType": "transit",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#757575"
      }
    ]
  },
  {
    "featureType": "water",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#000000"
      }
    ]
  },
  {
    "featureType": "water",
    "elementType": "labels.text",
    "stylers": [
      {
        "visibility": "off"
      }
    ]
  },
  {
    "featureType": "water",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#3d3d3d"
      }
    ]
  }
]

    });

    var infowindow = new google.maps.InfoWindow();
    var image = 'https://image.ibb.co/hws0ZK/slm_map_icon.png';
    var marker, i;

    for (i = 0; i < locations.length; i++) {
      marker = new google.maps.Marker({
        position: new google.maps.LatLng(locations[i][1], locations[i][2]),
        map: map,
        icon: image
      });

      google.maps.event.addListener(marker, 'click', (function(marker, i) {
        return function() {
          infowindow.setContent(locations[i][0]);
          infowindow.open(map, marker);


        }
      })(marker, i));
    }

  </script>

</body>
</html>
