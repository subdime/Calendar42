# Calendar42
This is a project for Calendar42 implementing a simple API Proxy for combining requests to the C42 server.  In order to create the requested functionality, the app has been designed as a simple view which is mapped to "/events-with-subscriptions/$EVENT_ID, which is accompanied by two classes, class "Request" which is responsible for making two different requests to the C42 API and class "RequestData" which handles the responses to obtain the necessary information. The data obtained from the two requests are combined in a JSON format and returned to the client.

The proxy has been implemented in Django framework as a seperate app within a project called C42, which could be the main project that the proxy is added to. This way, mapping in both the url.py files of the project and the app has been necessary. All default produced Django files have been included for completeness. The service has been impemented using the built-in development server of Django, which can be started with the command "python manage.py runserver" in the project folder. The app can return information only if the user enters the event_id provided for this project, which is hardcoded into the app files for comparison with user input. Finally the page is cached for 4.2 minutes after a request in order to avoid unnecessary calls to the C42 server, and the caching system used is local memory caching.

