# Markdig.Extensions.ScriptCs

This is an extension for Markdig that allows C# scripting to generate markdown or HTML content.

## Prerequisites

Instantiate the Markdig.Extensions.ScriptCs into the scripting runtime:

````C#
```ScriptCs
#r Markdig.Extensions.ScriptCs.dll
using Markdig.Extensions.ScriptCs;
```
````

This only needs to be done once in your document.

## Inline

##### Markdown:

```
This is some `ScriptCs MarkdownDocument.Instance.InsertMarkdown("_italic_");` text.
```

##### Output:

This is some _italic_ text.

##### Markdown:

```
This is some `ScriptCs MarkdownDocument.Instance.InsertHtml("<em>italic</em>");` text.
```

##### Output:

This is some _italic_ text.

## Code Block

##### Markdown:

````
```ScriptCs
MarkdownDocument.Instance.InsertMarkdown("Hello World!");
```
````

##### Output:

Hello World!

##### Markdown:

````
```ScriptCs
MarkdownDocument.Instance.InsertHtml("<p>Hello World!</p>");
```
````

##### Output:

Hello World!

## OxyPlot

##### Markdown:
````
```ScriptCs
#r OxyPlot.dll
#r System.Runtime.dll
using OxyPlot;
using OxyPlot.Series;
var myModel = new PlotModel { Title = "Example 1" };
myModel.Series.Add(new FunctionSeries(Math.Cos, 0, 10, 0.1, "cos(x)"));
var exporter = new SvgExporter { Width = 800, Height = 400 };
MarkdownDocument.Instance.InsertHtml(exporter.ExportToString(myModel));
```
````

##### Output:

<img src='data:image/svg+xml;utf8,%3Csvg%20width%3D%22800%22%20height%3D%22400%22%20version%3D%221.1%22%20xmlns%3Axlink%3D%22http%3A//www.w3.org/1999/xlink%22%20xmlns%3D%22http%3A//www.w3.org/2000/svg%22%3E%0A%20%20%3Cpolyline%20points%3D%2256.8495%2C370.947%2056.8495%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2271.7011%2C370.947%2071.7011%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2286.5526%2C370.947%2086.5526%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22101.4041%2C370.947%20101.4041%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22131.1072%2C370.947%20131.1072%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22145.9587%2C370.947%20145.9587%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22160.8102%2C370.947%20160.8102%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22175.6617%2C370.947%20175.6617%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22205.3648%2C370.947%20205.3648%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22220.2163%2C370.947%20220.2163%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22235.0678%2C370.947%20235.0678%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22249.9194%2C370.947%20249.9194%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22279.6224%2C370.947%20279.6224%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22294.4739%2C370.947%20294.4739%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22309.3255%2C370.947%20309.3255%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22324.177%2C370.947%20324.177%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22353.88%2C370.947%20353.88%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22368.7316%2C370.947%20368.7316%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22383.5831%2C370.947%20383.5831%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22398.4346%2C370.947%20398.4346%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22428.1377%2C370.947%20428.1377%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22442.9892%2C370.947%20442.9892%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22457.8407%2C370.947%20457.8407%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22472.6922%2C370.947%20472.6922%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22502.3953%2C370.947%20502.3953%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22517.2468%2C370.947%20517.2468%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22532.0983%2C370.947%20532.0983%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22546.9498%2C370.947%20546.9498%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22576.6529%2C370.947%20576.6529%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22591.5044%2C370.947%20591.5044%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22606.3559%2C370.947%20606.3559%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22621.2075%2C370.947%20621.2075%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22650.9105%2C370.947%20650.9105%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22665.762%2C370.947%20665.762%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22680.6136%2C370.947%20680.6136%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22695.4651%2C370.947%20695.4651%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22725.1681%2C370.947%20725.1681%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22740.0197%2C370.947%20740.0197%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22754.8712%2C370.947%20754.8712%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22769.7227%2C370.947%20769.7227%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22784.5742%2C370.947%20784.5742%2C374.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C350.8545%2030.498%2C350.8545%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C334.0953%2030.498%2C334.0953%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C317.3362%2030.498%2C317.3362%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C300.5771%2030.498%2C300.5771%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C267.0588%2030.498%2C267.0588%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C250.2996%2030.498%2C250.2996%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C233.5405%2030.498%2C233.5405%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C216.7814%2030.498%2C216.7814%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C183.2631%2030.498%2C183.2631%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C166.5039%2030.498%2C166.5039%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C149.7448%2030.498%2C149.7448%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C132.9857%2030.498%2C132.9857%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C99.4674%2030.498%2C99.4674%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C82.7082%2030.498%2C82.7082%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C65.9491%2030.498%2C65.9491%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C49.19%2030.498%2C49.19%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%2841.998%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E0%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28116.2556%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E1%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28190.5133%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E2%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28264.7709%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E3%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28339.0285%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E4%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28413.2861%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E5%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28487.5438%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E6%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28561.8014%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E7%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28636.059%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E8%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28710.3166%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E9%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28784.5742%2C381.947%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E10%3C/text%3E%0A%20%20%3Cpolyline%20points%3D%2241.998%2C370.947%2041.998%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22116.2556%2C370.947%20116.2556%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22190.5133%2C370.947%20190.5133%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22264.7709%2C370.947%20264.7709%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22339.0285%2C370.947%20339.0285%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22413.2861%2C370.947%20413.2861%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22487.5438%2C370.947%20487.5438%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22561.8014%2C370.947%20561.8014%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22636.059%2C370.947%20636.059%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22710.3166%2C370.947%20710.3166%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%22784.5742%2C370.947%20784.5742%2C377.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22middle%22%20text-anchor%3D%22end%22%20transform%3D%22translate%2823.498%2C367.6136%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E-1%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22middle%22%20text-anchor%3D%22end%22%20transform%3D%22translate%2823.498%2C283.8179%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E-0.5%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22middle%22%20text-anchor%3D%22end%22%20transform%3D%22translate%2823.498%2C200.0222%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E0%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22middle%22%20text-anchor%3D%22end%22%20transform%3D%22translate%2823.498%2C116.2265%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E0.5%3C/text%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22middle%22%20text-anchor%3D%22end%22%20transform%3D%22translate%2823.498%2C32.4308%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3E1%3C/text%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C367.6136%2027.498%2C367.6136%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C283.8179%2027.498%2C283.8179%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C200.0222%2027.498%2C200.0222%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C116.2265%2027.498%2C116.2265%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2234.498%2C32.4308%2027.498%2C32.4308%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolyline%20points%3D%2241.998%2C32.4308%2049.4238%2C33.2681%2056.8495%2C35.7715%2064.2753%2C39.916%2071.7011%2C45.6603%2079.1268%2C52.9469%2086.5526%2C61.7031%2093.9784%2C71.8412%20101.4041%2C83.2602%20108.8299%2C95.8457%20116.2556%2C109.4722%20123.6814%2C124.0034%20131.1072%2C139.2942%20138.5329%2C155.1917%20145.9587%2C171.5372%20153.3845%2C188.1673%20160.8102%2C204.9158%20168.236%2C221.6154%20175.6617%2C238.0993%20183.0875%2C254.2028%20190.5133%2C269.7648%20197.939%2C284.6301%20205.3648%2C298.6499%20212.7905%2C311.6843%20220.2163%2C323.6031%20227.6421%2C334.287%20235.0678%2C343.6294%20242.4936%2C351.5369%20249.9194%2C357.9306%20257.3451%2C362.7465%20264.7709%2C365.9364%20272.1966%2C367.4687%20279.6224%2C367.3278%20287.0482%2C365.5153%20294.4739%2C362.0493%20301.8997%2C356.9643%20309.3255%2C350.3112%20316.7512%2C342.1565%20324.177%2C332.5816%20331.6027%2C321.6822%20339.0285%2C309.5673%20346.4543%2C296.3578%20353.88%2C282.1857%20361.3058%2C267.1927%20368.7316%2C251.5286%20376.1573%2C235.3498%20383.5831%2C218.818%20391.0088%2C202.0984%20398.4346%2C185.3581%20405.8604%2C168.7643%20413.2861%2C152.4829%20420.7119%2C136.6764%20428.1377%2C121.5028%20435.5634%2C107.1138%20442.9892%2C93.6531%20450.4149%2C81.2553%20457.8407%2C70.044%20465.2665%2C60.1315%20472.6922%2C51.6168%20480.118%2C44.5848%20487.5438%2C39.1059%20494.9695%2C35.2349%20502.3953%2C33.0103%20509.821%2C32.4545%20517.2468%2C33.573%20524.6726%2C36.3545%20532.0983%2C40.7714%20539.5241%2C46.7795%20546.9498%2C54.3187%20554.3756%2C63.3137%20561.8014%2C73.6747%20569.2271%2C85.2981%20576.6529%2C98.0678%20584.0787%2C111.8561%20591.5044%2C126.5255%20598.9302%2C141.9291%20606.3559%2C157.9132%20613.7817%2C174.3181%20621.2075%2C190.9798%20628.6332%2C207.7318%20636.059%2C224.4068%20643.4848%2C240.8381%20650.9105%2C256.8617%20658.3363%2C272.3173%20665.762%2C287.0505%20673.1878%2C300.9142%20680.6136%2C313.7699%20688.0393%2C325.489%20695.4651%2C335.9544%20702.8909%2C345.0617%20710.3166%2C352.7198%20717.7424%2C358.8522%20725.1681%2C363.3976%20732.5939%2C366.3106%20740.0197%2C367.5622%20747.4454%2C367.1397%20754.8712%2C365.0474%20762.297%2C361.3063%20769.7227%2C355.9537%20777.1485%2C349.043%20784.5742%2C340.6434%22%20style%3D%22fill%3Anone%3Bstroke%3Argb%2878%2C154%2C6%29%3Bstroke-width%3A2%3Bstroke-linejoin%3Abevel%22%20/%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22middle%22%20transform%3D%22translate%28413.249%2C8%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2218%22%20font-weight%3D%22700%22%20fill%3D%22black%22%3EExample%201%3C/text%3E%0A%20%20%3Cpolygon%20points%3D%2234.498%2C29.0795%20792%2C29.0795%20792%2C370.947%2034.498%2C370.947%22%20style%3D%22fill%3Anone%3Bstroke%3Ablack%3Bstroke-width%3A1%22%20/%3E%0A%20%20%3Cpolygon%20points%3D%22723.502%2C37.0795%20784%2C37.0795%20784%2C63.1325%20723.502%2C63.1325%22%20style%3D%22fill%3Anone%3Bstroke%3Anone%3B%22%20/%3E%0A%20%20%3Ctext%20dominant-baseline%3D%22hanging%22%20text-anchor%3D%22start%22%20transform%3D%22translate%28751.502%2C45.0795%29%22%20font-family%3D%22Segoe%20UI%22%20font-size%3D%2212%22%20font-weight%3D%22400%22%20fill%3D%22black%22%3Ecos%28x%29%3C/text%3E%0A%20%20%3Cpolyline%20points%3D%22731.502%2C50.106%20747.502%2C50.106%22%20style%3D%22fill%3Anone%3Bstroke%3Argb%2878%2C154%2C6%29%3Bstroke-width%3A2%22%20/%3E%0A%3C/svg%3E'>



