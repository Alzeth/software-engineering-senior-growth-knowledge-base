__REST-ful API unnecessarily exposes models__

No models are exposed. Everything is handled by a single controller. The only thing that is exposed to the user is the route of the appropriate controller.

__REST-ful API forces one to think in terms of manipulating models instead of the natural behavior of stating intent__

Same as above. A single controller can handle the different customer happiness states. The distinction can be made by passing different post paramenters
(ex. { state: "happy"}).

__REST-ful API Update action oversimplifies too much__

Nothing stops you from manipulating the data that needs to be sent to your model before updating it. You can do whatever you want,
however complex it may be, before updating your model.

Finally, I believe that a RESTful API is only as good as its implementation. Furthermore, I believe that if you wanted to find a flaw to the REST
technique is the fact that you cannot initiate transactions or push notifications server-side

> <https://stackoverflow.com/questions/31164701/are-these-valid-disadvantages-of-a-rest-ful-api>
