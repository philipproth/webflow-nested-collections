# webflow_nested_collections
Add multiple nested collections without limitation of collectioniItems on a single page in a Webflow project.

An easy and lightweight way to nest multiple collections with unlimited items on any single page with jQuery .load() which pulls the multi-reference info from any individual page into an HTML embed, that works like a nested collection. 

This solution is based on the jQuery .load() function - a simple way to fetch data from a server and place the returned HTML into a matching element. 

For more details have a look at the sample blog pages in this project, read the short documentation (How to?) you'll find in this project and feel free to clone the whole project.

Clone and inspect this project (e.g. the blog example) or read this short documentation to start from scretch.

First step: Create a collection list on a CMS collection page and give the collection list element (not the collection list wrapper) an individual class. The collection list element will serve as the nested collection on your static pages and the class you've given to it serves as an indentifier to fetch the element with the jQuery .load() function.

Nested Collection in Webflow
Second step: Insert the following code snippet with HTLM embed into the collection list on your static page (e.g. your blog post overview) or into a collection list on another CMS collection page (e.g. the category or tag CMS template page). Place the HTML embed at the place where the nested collection list should appear.

<div class="authors-list" id="unify-[slug]"></div>
‍
<script>
window.addEventListener('DOMContentLoaded', function() {
   jQuery(function() {
       jQuery('#unify-[slug]').load("/post/[slug] .authors-list")
   });
});
</script>

Third step: Adjust the unify-[slug] part and the url-part in the code snippet (marked in purple and red). Replace [slug] with the dynamic slug element by using the "+ Add Field" in the upper right corner of the HTML Embed Code Editor. Replace unify- with an individual piece of text to get an individual ID for each nested collection list. This step is important if you use multiple nested collections within the parent collection (e.g. authors, tags and categories). Adjust the URL in the code snippet to point to the CMS template page that contains the collection you want to embed as a nested collection. Therefore, use the dynamic slug element (+ Add Field" in the upper right corner of the HTML Embed Code Editor). Finally you have to adjust the class (marked in blue). Use the class you gave to the collection list you want to nest (see first step above). In this example this is the class .authors-list.

Demo site and clonable Webflow project https://multiple-nested-collections.webflow.io/
