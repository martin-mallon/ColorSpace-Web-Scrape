<h1>ColorSpace Web Scrape</h1>

<br>

<p align="center" width="100%">
    <img width="100%" src="/ColorSpace_Scrape/Generic Gradient.png">
</p>

<br>

<h3>Overview</h3>
  
<p>ColorSpace provides 25 palettes based on a user-inputted base color. This app allows users to dynamically pull palettes from ColorSpace and apply the hex codes to data visualisations. This is achieved with the </code>colorspace</code> function which asks the user to select a <code>hex_base</code> code (e.g. teal '89F4EC') and uses the <code>requests</code> & <code>BeautifulSoup</code> libraries to scrape the palettes and hex codes which can be accessed via a dictionary of lists.</p>

<br>

<h3>Instructions</h3>

<ul>
    <li><code>ColorSpace.ipynb</code> - Integrate the <code>.ipynb</code> into a work environment. This script contains the <code>colorspace</code> function that scrapes the page content.</li>
    <br>
    <li><code>import the colorspace function</code> - Import the <code>colorspace</code> function into the current desired notebook with:</li>
</ul>

<br>

```
# import ColorSpace function
from ipynb.fs.full.ColorSpace import colorspace
```

<br>

<ul>
    <li><code>hex_base</code> - Define the base color hex code to derive palettes (e.g. teal '89F4EC'). <b>NB.</b> Do not include # in the base code.</li>
</ul>

```
# select hex code
hex_base = '89F4EC'
```

<br>

<ul>
    <li><code>colorspace(hex_base)</code> - Call the <code>colorspace</code> function using the <code>hex_base</code> to produce a dictionary of palettes and constintuent hex codes.</li>
</ul>

```
# run the function
palettes = colorspace(hex_base)
palettes
```

```
>> Output
{'Generic Gradient': ['#89f4ec', '#88fadb', '#97fdc2', '#b2fea6', '#d3fd8a', '#f9f871'],
 'Matching Gradient': ['#89f4ec', '#54d6f2', '#51b4ef', '#768ed8', '#9663ab', '#9e386e'],
 'Spot Palette': ['#89f4ec', '#4dbbb4', '#c0fcf7', '#99005d'],
 'Twisted Spot Palette': ['#89f4ec', '#b70075', '#ffe4f8', '#b08598'],
 'Classy Palette': ['#89f4ec', '#334b49', '#95b1ae', '#adc6ff', '#7690ca'],
 'Cube Palette': ['#89f4ec', '#00c48f', '#545479'],
 'Switch Palette': ['#89f4ec', '#00413e', '#b70075', '#e8f3f1'],
 'Small Switch Palette': ['#89f4ec', '#def6ec', '#499176'],
 'Skip Gradient': ['#89f4ec', '#a3f6a8', '#6cbd73', '#358742'],
 'Natural Palette': ['#89f4ec', '#00aaa1', '#e9fdfb', '#e8f3f1'],
 'Matching Palette': ['#89f4ec', '#334b49', '#95b1ae', '#ffccef', '#df95b7'],
 'Squash Palette': ['#89f4ec', '#ffa8fc', '#cccb67'],
 'Grey Friends': ['#89f4ec', '#334b49', '#95b1ae'],
 'Dotting Palette': ['#89f4ec', '#95b1ae', '#adc6ff', '#a5abbd'],
 'Skip Shade Gradient': ['#89f4ec', '#86f6da', '#90f7c2', '#a3f6a8'],
 'Threedom': ['#89f4ec', '#d0a7fe', '#e0a15c'],
 'Highlight Palette': ['#89f4ec', '#00ada4', '#e8f3f1', '#545479'],
 'Neighbor Palette': ['#89f4ec', '#00c48f', '#3c846a', '#374b43'],
 'Discreet Palette': ['#89f4ec', '#00aaa1', '#e5fffc', '#545479'],
 'Dust Palette': ['#89f4ec', '#334b49', '#95b1ae', '#adc6ff'],
 'Collective': ['#89f4ec', '#00c1db', '#9ac6ff'],
 'Friend palette': ['#89f4ec', '#00534f', '#b70075', '#ff70c5'],
 'Pin Palette': ['#89f4ec', '#00ada4', '#e8f3f1', '#f353a9'],
 'Shades': ['#89f4ec', '#54c1ba', '#0c908a', '#00625d', '#003734'],
 'Random Shades': ['#89f4ec', '#004945', '#6fdad3', '#038d87', '#00716c']}
```

<br>

<ul>
    <li><code>Select & apply a palette</code> - Filter the <code>palettes</code> dictionary and assign to a variable that is used in data visualisation.</li>
</ul>

```
# run the function
p = palettes['Shades']
sns.lineplot(data=df, x='n', y='y', hue='grp', palette=p)
```

<p align="center" width="100%">
    <img width="100%" src="/ColorSpace_Scrape/Shades.png">
</p>
