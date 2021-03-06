# HeaderTableLayoutPanel

HeaderTableLayoutPanel is a WinForms control inherited from TableLayoutPanel and provides highlighted header.

## Problem

There are a lot of panels for grouping the controls in WinForms. The best one of them is _TableLayoutPanel_, especially for grouping controls, that are using for editing data. Unfortunately, this panel does not show the header. This necessity appears when there are different kinds of editing controls on the same Windows form.

## Solution

It can be solved by _GroupBox_ and _TableLayoutPanel_. This solution is easy, but may look unpleasant. Another possibility is using _Label_ control in first row of _TableLayoutPanel_. This solution may be uncomfortable.

I prefer to make inherited panel from _TableLayoutPanel_ with all necessary functions.

## How It works

TableLayoutPanel with highlighted header called _HeaderTableLayoutPanel_ is simple, useful, and cute. This control may show the header in a number of different ways:

![How It works](Media/img_01.png)

The _HeaderTableLayoutPanel_ implements just three properties:
- _CaptionText_ - string property that contains a text for showing. If this property is _string.Empty_ or _null_ then the header will not be shown
- _CaptionStyle_ - this is enum (_HighlightCaptionStyle_) property that points a drawing style. It can be: _ForeColor_, _HighlightColor_, _ForeStyle_, _HighlightStyle_, _NavisionAxaptaStyle_, _GroupBoxStyle_ (see the image above)
- _CaptionLineWidth_ - byte property that points the width of header's line (0 - the line will not be shown)

Be aware of _CaptionLineWidth_. If _CaptionStyle = HighlightCaptionStyle.HighlightStyle_, then two lines with _Width = CaptionLineWidth_ will be shown, one will be above the Header and the second one will be below the header. For _CaptionStyle = HighlightCaptionStyle.GroupBoxStyle_ this property does not do anything. 

#### Screens

![Screen 1](Media/img_02.png)
![Screen 2](Media/img_03.png)
![Screen 3](Media/img_04.png)

## How to use it

The following example explains the procedure to create a new HeaderTableLayoutPanel:
```
using CBComponents;
...
var headerTableLayoutPanel = new HeaderTableLayoutPanel()
{
  CaptionText = "Preferred text for header",
  CaptionStyle = HeaderTableLayoutPanel.HighlightCaptionStyle.NavisionAxaptaStyle,
  CaptionLineWidth = 2  
};
this.Controls.Add(headerTableLayoutPanel1);
```
To install _HeaderTableLayoutPanel_, run the following command in the [Package Manager Console](https://www.nuget.org/packages/CBComponents.HeaderTableLayoutPanel):
```
PM> Install-Package CBComponents.HeaderTableLayoutPanel 
```
Alternative option: [download compiled library and examples](https://github.com/CanadianBeaver/HeaderTableLayoutPanel/raw/master/Build/CBComponents.HeaderTableLayoutPanel.zip).

## Supported .NET Frameworks

_HeaderTableLayoutPanel_ inherits from [_TableLayoutPanel_](https://msdn.microsoft.com/library/system.windows.forms.tablelayoutpanel), which was implemented in Microsoft .NET Framework 3.5. In general _HeaderTableLayoutPanel_ does not use any special requirements. It can be compiled on any Microsoft .NET Framework platform (including the .NET Framework 3.5 client profile).

## Contacts

I would appreciate hearing your opinion on this. If you have any questions, please feel free to contact me by email: [radu.martin@hotmail.com](mailto://radu.martin@hotmail.com)
