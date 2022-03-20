## Creating Maps with Google's Map Styling Wizard

## Getting Started

For this assignment, I chose to develop a map for the National Audubon Society ("Audubon"), a non-profit dedicated to the conservation and study of birds and their habitats. While the organization consists primarily of enthusiastic ornithologists and conservationists, they rely heavily on the participation of the general public -- amateur birders and donors both have a role to play in the conservation movement. 

The organization does not have a consistent or clear visual style. While the images of regional birds are colorful and draw the eye, the maps included on their website, such as this [depiction of their national network](https://www.audubon.org/about/audubon-near-you), already look a bit out of place and have fairly chaotic coloring. This encouraged me to attempt to style a map based on one of the images they were already sharing on their website.  

I took a screenshot of Audobon's [Guide to North American Birds](https://www.audubon.org/bird-guide), which features a Cedar Waxwing. The color on this bird seemed to be the most dynamic, and I thought it would give me a more flexible palette to play around with. 

Adobe generated the following palette from the image: 

<img src="https://github.com/nannunz/gis-portfolio/blob/main/waxwing%20palette.png?raw=true"> 

In order to input the colors into the Styling Wizard, the Hex Codes needed to be converted into an RGB format:
<iframe title="Audubon Palette (Hex Code-RGB Conversion)" aria-label="Table" id="datawrapper-chart-m6i9y" src="https://datawrapper.dwcdn.net/m6i9y/1/" scrolling="no" frameborder="0" style="border: none;" width="600" height="306"></iframe>

## Creating the Map 


The final map: 

[
  {
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#d1d8e4"
      }
    ]
  },
  {
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#523735"
      }
    ]
  },
  {
    "elementType": "labels.text.stroke",
    "stylers": [
      {
        "color": "#f5f1e6"
      }
    ]
  },
  {
    "featureType": "administrative",
    "elementType": "geometry.stroke",
    "stylers": [
      {
        "color": "#c9b2a6"
      }
    ]
  },
  {
    "featureType": "administrative.land_parcel",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#8c7158"
      },
      {
        "saturation": -65
      },
      {
        "lightness": 65
      }
    ]
  },
  {
    "featureType": "administrative.land_parcel",
    "elementType": "geometry.fill",
    "stylers": [
      {
        "color": "#8c7158"
      },
      {
        "saturation": -35
      },
      {
        "lightness": 65
      }
    ]
  },
  {
    "featureType": "administrative.land_parcel",
    "elementType": "geometry.stroke",
    "stylers": [
      {
        "color": "#8c7158"
      },
      {
        "saturation": -70
      },
      {
        "lightness": 55
      }
    ]
  },
  {
    "featureType": "administrative.land_parcel",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#8c7158"
      }
    ]
  },
  {
    "featureType": "landscape.natural",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#e7dfd8"
      },
      {
        "saturation": -10
      },
      {
        "lightness": 10
      }
    ]
  },
  {
    "featureType": "poi",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#93817c"
      }
    ]
  },
  {
    "featureType": "poi.park",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#f2b705"
      }
    ]
  },
  {
    "featureType": "poi.park",
    "elementType": "geometry.fill",
    "stylers": [
      {
        "saturation": 15
      }
    ]
  },
  {
    "featureType": "poi.park",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#8c7158"
      },
      {
        "saturation": 30
      },
      {
        "lightness": -45
      }
    ]
  },
  {
    "featureType": "road",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#276573"
      },
      {
        "lightness": 45
      }
    ]
  },
  {
    "featureType": "road.arterial",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#bf2c2c"
      }
    ]
  },
  {
    "featureType": "road.arterial",
    "elementType": "geometry.fill",
    "stylers": [
      {
        "color": "#bf2c2c"
      },
      {
        "lightness": 45
      }
    ]
  },
  {
    "featureType": "road.arterial",
    "elementType": "geometry.stroke",
    "stylers": [
      {
        "color": "#bf2c2c"
      }
    ]
  },
  {
    "featureType": "road.highway",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#8c7158"
      }
    ]
  },
  {
    "featureType": "road.highway",
    "elementType": "geometry.fill",
    "stylers": [
      {
        "color": "#8c7158"
      }
    ]
  },
  {
    "featureType": "road.highway",
    "elementType": "geometry.stroke",
    "stylers": [
      {
        "color": "#8c7158"
      }
    ]
  },
  {
    "featureType": "road.highway.controlled_access",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#8c7158"
      }
    ]
  },
  {
    "featureType": "road.highway.controlled_access",
    "elementType": "geometry.stroke",
    "stylers": [
      {
        "color": "#8c7158"
      }
    ]
  },
  {
    "featureType": "road.local",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#bf2c2c"
      }
    ]
  },
  {
    "featureType": "road.local",
    "elementType": "geometry.fill",
    "stylers": [
      {
        "color": "#bf2c2c"
      }
    ]
  },
  {
    "featureType": "road.local",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#806b63"
      }
    ]
  },
  {
    "featureType": "transit.line",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#bf2c2c"
      }
    ]
  },
  {
    "featureType": "transit.line",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#8c7158"
      }
    ]
  },
  {
    "featureType": "transit.line",
    "elementType": "labels.text.stroke",
    "stylers": [
      {
        "color": "#ebe3cd"
      }
    ]
  },
  {
    "featureType": "transit.station",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#bf2c2c"
      },
      {
        "saturation": -35
      },
      {
        "lightness": 25
      }
    ]
  },
  {
    "featureType": "water",
    "elementType": "geometry",
    "stylers": [
      {
        "color": "#348798"
      }
    ]
  },
  {
    "featureType": "water",
    "elementType": "geometry.fill",
    "stylers": [
      {
        "color": "#338697"
      }
    ]
  },
  {
    "featureType": "water",
    "elementType": "labels.text.fill",
    "stylers": [
      {
        "color": "#8c7158"
      }
    ]
  }
]


## Next Steps 



## My Initial Failed Attempt 


[Return to portfolio homepage](https://nannunz.github.io/gis-portfolio/)
