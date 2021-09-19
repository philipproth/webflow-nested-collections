# Webflow nested collections without limitations.

Add multiple nested collections in a Webflow project without the default limitation of max 1 collection list per static page with max 5 collection items on any static single page.

## Intro
An easy and lightweight way to nest multiple collections with unlimited items on any single page with jQuery .load() which pulls the multi-reference info from any individual page into an HTML embed, that works like a nested collection. 

This solution is based on the jQuery .load() function - a simple way to fetch data from a server and place the returned HTML into a matching element. 

For more details have a look at the [sample project] (https://multiple-nested-collections.webflow.io/) and read the [short documentation] (https://multiple-nested-collections.webflow.io/documentation). Feel free to clone the whole project at [Webflow Showcase] (https://webflow.com/website/Multiple-nested-Collections-with-unlimited-Items-on-single-pages-in-Webflow).

## How to set it up

**First step:** Create a collection list on a CMS collection page and give the collection list element (not the collection list wrapper) an individual class. The collection list element will serve as the nested collection on your static pages and the class you've given to it serves as an indentifier to fetch the element with the jQuery .load() function.

**Second step:** Insert the following code snippet with HTLM embed into the collection list on your static page (e.g. your blog post overview) or into a collection list on another CMS collection page (e.g. the category or tag CMS template page). Place the HTML embed at the place where the nested collection list should appear.

```
<div class="collection-list" id="unify-[webflow-dyn-slug]"></div>
‍
<script>
window.addEventListener('DOMContentLoaded', function() {
   jQuery(function() {
       jQuery('#unify-[webflow-dyn-slug]').load("/post/[webflow-dyn-slug] .collection-list")
   });
});
</script>
```

**Third step:** Adjust the unify-[slug] part and the url-part in the code snippet (marked in purple and red). Replace [slug] with the dynamic slug element by using the "+ Add Field" in the upper right corner of the HTML Embed Code Editor. Replace unify- with an individual piece of text to get an individual ID for each nested collection list. This step is important if you use multiple nested collections within the parent collection (e.g. authors, tags and categories). Adjust the URL in the code snippet to point to the CMS template page that contains the collection you want to embed as a nested collection. Therefore, use the dynamic slug element (+ Add Field" in the upper right corner of the HTML Embed Code Editor). Finally you have to adjust the class (marked in blue). Use the class you gave to the collection list you want to nest (see first step above). In this example this is the class .authors-list.

## Demo and clonable project

Clone the demo project and inspect the blog overview page to gain a better understanding for nesting collection lists and collection items with jQuery .load() in Webflow.

[Demo site and clonable Webflow project] (https://multiple-nested-collections.webflow.io/)
