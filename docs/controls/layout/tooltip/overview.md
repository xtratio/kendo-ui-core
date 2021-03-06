---
title: Overview
page_title: Overview | Kendo UI Tooltip Widget
description: "Learn how to initialize the Kendo UI Tooltip widget and configure its behaviors."
slug: overview_kendoui_tooltip_widget
position: 1
---

# Tooltip Overview

The [Kendo UI Tooltip widget](http://demos.telerik.com/kendo-ui/tooltip/index) displays a popup hint for a given `html` element. Its content can be defined either as static text, or loaded dynamically via AJAX.

## Getting Started

### Initialize the Tooltip

The Tooltip can be initialized:

* For a single element
* For a container, where child elements are going to represent Tooltip targets


#### Initialize Tooltip for single elements

The example below demonstrates how to create a Tooltip for a single target and initialize it.

###### Example

    <div id="target">
        Some Content
    </div>

    $(document).ready(function() {
        $("#target").kendoTooltip({ content: "Tooltip content" });
    });

#### Initialize Tooltip for containers

The example below demonstrates how to create a Tooltip for multiple targets within a container, initialize it using a jQuery selector and specfy the filter to match the target elements. By default, the Tooltip content is extracted from the `title` attribute of the target element.

###### Example

    <div id="container">
        Some <a href="#" title="Some text">Content</a><br />
        Some <a href="#" title="Some other text">More</a> Content <br />
    </div>  

    $(document).ready(function() {
        $("#container").kendoTooltip({ filter: "a[title]" });
    });

## Configuration

### Defaults

Kendo UI Tooltip provides default configuration options that can be set during initialization. Some of the properties that can be overriden and controlled are:

*   Content
*   Position relative to the target (top, botton, center, left, right)
*   Event on which the Tooltip si going to be displayed
*   Auto-hide behavior
*   Height/Width

The example below demonstrates how to intiialize a Tooltip and configure its main propertues.

###### Example

    $("#container").kendoTooltip({
        position: "right",
        height: "300px",
        showOn: "click",
        autoHide: true,
        content: function() {
            return "custom text";
        },
        width: "500px"
    });

### Load Content with AJAX

A Kendo UI Tooltip widget provides built-in support for asynchronously loading content from a URL. This URL is expected to return an HTML fragment that can be loaded in a Tooltip content area. If the content passed to the Tooltip includes scripts, they are going to be executed.

The example below demonstrates how to asynchronously load content to the Tooltip.

###### Example

    <div id="target">Content Text</div>

    $(document).ready(function(){
        $("#target").kendoTooltip({
            content: { url: "html-content-snippet.html" }
        });
    });

## Reference

### Existing Instances

Refer to an existing Tooltip instance via the [`jQuery.data()`](http://api.jquery.com/jQuery.data/). Once a reference has been established, use the [Tooltip API](/api/javascript/ui/tooltip) to control its behavior.

The example below demonstrates how to access an existing Tooltip instance.

###### Example

    var tooltip = $("#target").data("kendoTooltip");

## See Also

Other articles on Kendo UI Tooltip:

* [Overview of the ASP.NET MVC HtmlHelper Extension](/aspnet-mvc/helpers/tooltip/overview)
* [Overview of the JSP Tag](/jsp/tags/tooltip/overview)
* [Overview of the PHP Class](/php/widgets/tooltip/overview)
* [How to Calculate Tooltip Content Width]({% slug howto_calculatetooltipcontentlength_tooltip %})
* [How to Show Only If Text Exceeds Certain Length]({% slug howto_showonlyiftextexceedscertainlength_tooltip %})
* [How to Show Only If Text Overflows with Ellipsis]({% slug howto_showonlyiftextoverflowswithellipsis_tooltip %})
* [JavaScript API Reference](/api/javascript/ui/tooltip)
