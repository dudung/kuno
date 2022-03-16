# physics
Physics in plain text

## Log
[`08 Aug 2020`]() Create transparent icon using https://www.favicon.cc/?
[`26 Jul 2020`]() Continue creating simple contents in besaran dan satuan, create header. <br />
[`25 Jul 2020`]() Copy `butiran/docs`, setup configuration, adjust the content, and up the site. <br />

### test math
\begin{equation}
y = ax^2 + bx + c
\end{equation}

```math
y = ax^2 + bx + c
```

### test mermaid
```mermaid
  graph TD;
      A-->B;
      A-->C;
      B-->D;
      C-->D;
```

### test xhub
```chartjs
{
  "config": {
    "type": "line",
    "data": {
      "labels": [1500,1600,1700,1750,1800,1850,1900,1950,1999,2050],
      "datasets": [{
          "data": [86,114,106,106,107,111,133,221,783,2478],
          "label": "Africa",
          "borderColor": "#3e95cd",
          "fill": false
        }, {
          "data": [282,350,411,502,635,809,947,1402,3700,5267],
          "label": "Asia",
          "borderColor": "#8e5ea2",
          "fill": false
        }, {
          "data": [168,170,178,190,203,276,408,547,675,734],
          "label": "Europe",
          "borderColor": "#3cba9f",
          "fill": false
        }, {
          "data": [40,20,10,16,24,38,74,167,508,784],
          "label": "Latin America",
          "borderColor": "#e8c3b9",
          "fill": false
        }, {
          "data": [6,3,2,2,7,26,82,172,312,433],
          "label": "North America",
          "borderColor": "#c45850",
          "fill": false
        }
      ]
    },
    "options": {
      "title": {
        "display": true,
        "text": "World population per region (in millions)"
      }
    }
  }
}
```

```plotly
{
  "data": [
    {
      "line": {"shape": "linear"},
      "mode": "lines+markers",
      "name": "linear",
      "type": "scatter",
      "x": [1, 2, 3, 4, 5],
      "y": [1, 3, 2, 3, 1],
      "hoverinfo": "name"
    },
    {
      "line": {"shape": "spline"},
      "mode": "lines+markers",
      "name": "spline",
      "type": "scatter",
      "x": [1, 2, 3, 4, 5],
      "y": [6, 8, 7, 8, 6],
      "text": ["tweak line smoothness<br>with 'smoothing' in line object"],
      "hoverinfo": "text+name"
    },
    {
      "line": {"shape": "vhv"},
      "mode": "lines+markers",
      "name": "vhv",
      "type": "scatter",
      "x": [1, 2, 3, 4, 5],
      "y": [11, 13, 12, 13, 11],
      "hoverinfo": "name"
    },
    {
      "line": {"shape": "hvh"},
      "mode": "lines+markers",
      "name": "hvh",
      "type": "scatter",
      "x": [1, 2, 3, 4, 5],
      "y": [16, 18, 17, 18, 16],
      "hoverinfo": "name"
    },
    {
      "line": {"shape": "vh"},
      "mode": "lines+markers",
      "name": "vh",
      "type": "scatter",
      "x": [1, 2, 3, 4, 5],
      "y": [21, 23, 22, 23, 21],
      "hoverinfo": "name"
    },
    {
      "line": {"shape": "hv"},
      "mode": "lines+markers",
      "name": "hv",
      "type": "scatter",
      "x": [1, 2, 3, 4, 5],
      "y": [26, 28, 27, 28, 26],
      "hoverinfo": "name"
    }
  ],
  "layout": {
    "legend": {
      "y": 0.5,
      "font": {"size": 16},
      "traceorder": "reversed"
    }
  }
}
```
