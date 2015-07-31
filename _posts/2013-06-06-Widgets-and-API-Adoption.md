---
layout: post
title: Widgets and API Adoption
tags: [All Things Tech]
image: 

bio: 
 
biopic: 

featured-summary:
    <p>Widgets and API Adoption</p>

summary: 

---
The Edmunds API has been live for almost two years now, boasting over 1,300 active developers and 250+ live applications. Individual developers and large firms are using the API to build creative automotive experiences for their customers. Companies like eBay, Toyota and the automotive tech agency, Nexteppe, are a few that come to mind.

But in order to build out a custom API-based experience, like these guys did, one needs to possess a certain level of web development expertise and resource commitment. Based on our experience, not everyone interested in our data is capable of that. Some of our partners just want to "put the API on their web page". That's a direct quote.

<b> SO WHY WIDGETS? </b>

After getting a large number of these requests to "just put the API on the page", we went to the drawing board to address that need. These requests were coming from some of our partners (mostly dealerships), which made them a high priority for us. Our solution had to satisfy the following three conditions:

1. Self-serve: in order for the solution to be scalable, it had to be easily deployable. We [Edmunds.com] cannot be the bottleneck in its adoption.
2. Configurable: allow partners using this solution to customize it enough to make it their own without having us creating one-offs for them that aren't maintainable.
3. Embeddable: the solutions needs to be embedded on the partner's website using web technology (i.e. Javascript)

With that mind, we landed on API Widgets: configurable, self-contained, easy-to-embed automotive solutions built in Javascript.

Widgets are nothing new, of course, and that familiarity helped tip our decision in their favor. We didn't want a novel solution that confused partners and required them to learn yet a new way of doing things. We wanted a tried-and-true solution that everyone's familiar with and widgets satisfied that criterion fully.

<b> THE EDMUNDS API WIDGETS </b>

We currently have two widgets: The True Market ValueÂ® (TMV) and the New Vehicle Configurator widgets. Both widgets were built based on a set of feature requests were received directly from partners. Therefore, both widgets are currently being used by those partners who otherwise wouldn't have been able to use our API.

Each widget offers the following:

1. Widget Configuration: We identify parts of the widget that the client would or could change and made it configurable.
2. Live Demo: Widget can be interacted with while being configured. Clients can see what they'll get before embedding anything on their page.
3. Custom Events: All actions happening within the widget (dropdown value selected, car photo is displayed, price is calculated, ...etc) can be subscribed to in order to extend the widget's functionality.
4. Documentation: To be completely self-serve, full documentation of how to install, configure and extend the widget is provided.
The New Vehicle Configurator widget allows the consumer to pick a new vehicle, select its color and options and get pricing on it for a specific zip code before submitting a request for a price quote to nearby dealers.

The TMV® widget is a basic pricing widget for new and used vehicles giving the consumer an idea of how much others have paid for a similar vehicle in their area. The widget also offers a trade-in price range for used vehicles (a highly requested feature).

We will continue to build widgets (we have two more in development) to ensure a wider API adoption. Even better, we will be releasing the widget SDK very soon so developers can also build widgets that are easy for clients to install. We're in effect removing ourselves as the bottleneck of widget development by staying true to putting the power in the developer hand.

For more Edmunds API news and updates, follow us on Twitter @EdmundsAPI

Happy Coding!
