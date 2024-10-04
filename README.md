### Q1: What are the two approaches to creating APIs in ASP.NET Core?
**Ans:** Controller-based APIs and minimal APIs.

### Q2: How do controllers in an API project typically take dependencies?
**Ans:** Controllers take dependencies via constructor injection or property injection.

### Q3: What is the purpose of minimal APIs in ASP.NET Core?
**Ans:** Minimal APIs simplify API development by focusing on configuration and extensibility via extension methods and lambda expressions.

### Q4: What is the primary difference between controller-based APIs and minimal APIs in terms of structure?
**Ans:** Controller-based APIs use classes that derive from `ControllerBase`, whereas minimal APIs define endpoints with logical handlers using lambdas or methods, without explicit controller classes.

### Q5: How do minimal APIs support dependency injection?
**Ans:** Minimal APIs access the service provider directly or use other approaches to achieve dependency injection.

### Q6: Provide a sample code structure for a controller-based API project in ASP.NET Core.
**Ans:** The sample structure includes the creation of a `WebApplication` object, adding controller services, and mapping the controllers via `app.MapControllers()`.

### Q7: How are endpoints defined in a minimal API project?
**Ans:** Endpoints are defined in-line using lambda expressions, for example, `app.MapGet("/route", handler)`.

### Q8: How can a WeatherForecast API be implemented using controllers?
**Ans:** A `WeatherForecastController` class is created that defines a `Get` method to return an array of weather forecasts using a predefined set of summaries and random data.

### Q9: How does the minimal API approach define routes and logic?
**Ans:** Routes and logic are defined inline using `app.MapGet()` and lambda functions without separate controller classes.

### Q10: What class is used in both API approaches to represent weather data?
**Ans:** The `WeatherForecast` class.

### Q11: How does the `TemperatureF` property calculate the Fahrenheit value in the WeatherForecast class?
**Ans:** The formula used is `32 + (int)(TemperatureC / 0.5556)`.

### Q12: What are some capabilities that minimal APIs share with controller-based APIs?
**Ans:** Both support scaling to multiple APIs, handling complex routes, applying authorization, and controlling API response content.

### Q13: What are some features not supported by minimal APIs?
**Ans:** Features like built-in model binding, validation, application parts, custom conventions, view rendering, and OData are not supported by minimal APIs.

### Q14: What is the `IModelBinderProvider` in ASP.NET Core?
**Ans:** It's an interface used to provide model binders in a controller-based API.

### Q15: What is the purpose of the `IModelValidator` in a controller-based API?
**Ans:** It provides validation logic for models.

### Q16: Why are Razor Pages recommended for rendering views instead of minimal APIs?
**Ans:** Minimal APIs do not support view rendering, while Razor Pages are designed for that purpose.

### Q17: What is the `JsonPatch` operation, and why isn’t it supported by minimal APIs?
**Ans:** `JsonPatch` is used to partially update JSON objects, and minimal APIs lack built-in support for it.

### Q18: In a web API, why should controllers derive from `ControllerBase`?
**Ans:** `ControllerBase` provides essential methods for handling HTTP requests without the overhead of view rendering, which is unnecessary for APIs.

### Q19: What additional functionality does the `Controller` class provide compared to `ControllerBase`?
**Ans:** The `Controller` class adds support for views, which is useful for web pages but not for APIs.

### Q20: How does the `CreatedAtAction` method in a controller handle HTTP responses?
**Ans:** It returns a 201 status code and a link to the newly created resource.

### Q21: What does the `BadRequest` method return in ASP.NET Core controllers?
**Ans:** It returns a 400 status code, indicating a bad request.

### Q22: What is the purpose of the `NotFound` method in a controller-based API?
**Ans:** It returns a 404 status code when a requested resource cannot be found.

### Q23: How does the `[ApiController]` attribute change controller behavior?
**Ans:** It enforces attribute routing, automatic 400 responses for validation errors, and binding source inference.

### Q24: What does attribute routing enforce when using `[ApiController]` in ASP.NET Core?
**Ans:** It requires all routes to be defined using attributes like `[Route]`.

### Q25: How does the `[HttpGet]` attribute work in a controller-based API?
**Ans:** It maps an action method to the HTTP GET verb.

### Q26: What is the role of the `[Consumes]` attribute in an API controller?
**Ans:** It specifies the types of data that an action can accept, such as JSON or XML.

### Q27: How does the `[Produces]` attribute define the return data type of a controller action?
**Ans:** It specifies the types of data that the action will return, such as JSON or XML.

### Q28: How does automatic HTTP 400 response handling work with the `[ApiController]` attribute?
**Ans:** Validation errors trigger an automatic HTTP 400 response without needing explicit checks in the code.

### Q29: Why is the `ModelStateInvalidFilter` used in ASP.NET Core MVC?
**Ans:** It checks for model validation errors and automatically returns a 400 status if validation fails.

### Q30: What is the `ValidationProblemDetails` object used for in ASP.NET Core?
**Ans:** It provides a standardized format for validation errors in web API responses.

### Q31: How can you log automatic 400 responses in an API controller?
**Ans:** By configuring the `InvalidModelStateResponseFactory` delegate to log validation errors before the 400 response is returned.

### Q32: How can you disable the automatic HTTP 400 response behavior in a controller?
**Ans:** Set `SuppressModelStateInvalidFilter` to `true` in `ApiBehaviorOptions`.

### Q33: What is binding source parameter inference in ASP.NET Core?
**Ans:** ASP.NET Core infers the binding source for action parameters based on their type and usage.

### Q34: What is the role of the `[FromBody]` attribute in API controller parameters?
**Ans:** It specifies that the parameter's value should be read from the body of the HTTP request.

### Q35: What types of parameters should use the `[FromRoute]` attribute?
**Ans:** Parameters whose values are part of the URL route.

### Q36: How does `[FromQuery]` handle query string parameters in an API action?
**Ans:** It binds action method parameters to query string values in the URL.

### Q37: What is inferred by the `[FromServices]` attribute in ASP.NET Core?
**Ans:** It indicates that a parameter should be provided by dependency injection.

### Q38: How can you prevent automatic binding source inference for a specific parameter?
**Ans:** By explicitly applying a binding attribute, such as `[FromBody]` or `[FromQuery]`, to the parameter.

### Q39: How can automatic binding source inference be disabled globally in an ASP.NET Core application?
**Ans:** Set `DisableImplicitFromServicesParameters` to `true` in `ApiBehaviorOptions`.

### Q40: How does the ASP.NET Core runtime handle complex object binding by default?
**Ans:** It attempts to bind complex objects from multiple sources, such as query strings and route data, unless a specific binding source is defined.
g### Q34: How can you disable automatic binding source inference for a specific parameter?
**Ans:** By explicitly applying a binding attribute, such as `[FromBody]` or `[FromQuery]`, to the parameter.

### Q35: How can automatic binding source inference be disabled globally in an ASP.NET Core application?
**Ans:** Set `DisableImplicitFromServicesParameters` to `true` in `ApiBehaviorOptions`.

### Q36: How does the ASP.NET Core runtime handle complex object binding by default?
**Ans:** It attempts to bind complex objects from multiple sources, such as query strings and route data, unless a specific binding source is defined.

### Q37: How can you disable automatic DI for parameters in a controller action?
**Ans:** By applying a binding source attribute (e.g., `[FromBody]`) to the parameter.

### Q38: What is the role of the `IServiceProviderIsService` in ASP.NET Core?
**Ans:** It checks at app startup whether an argument in a controller action comes from DI or other sources.

### Q39: What is the significance of `BindingInfo.BindingSource` when handling parameter binding?
**Ans:** It ensures that once a binding source is set, it is not overwritten during parameter binding.

### Q40: How does ASP.NET Core assign `BindingSource.Query` to parameters?
**Ans:** Parameters that are not matched to routes, services, or the request body are assigned `BindingSource.Query`.

### Q41: What is the `SuppressInferBindingSourcesForParameters` property used for?
**Ans:** It disables automatic inference of binding sources for parameters.

### Q42: How does ASP.NET Core infer the binding source for complex types not registered in the DI container?
**Ans:** It infers `BindingSource.Body` for such types.

### Q43: What is the purpose of the `SuppressModelStateInvalidFilter` in API behavior options?
**Ans:** It disables the automatic model validation check that triggers a 400 response.

### Q44: How does the `SuppressMapClientErrors` property affect error mapping in API behavior?
**Ans:** It prevents automatic mapping of client errors, allowing custom error responses.

### Q45: How can you map custom client error links, such as for 404 errors, in ASP.NET Core?
**Ans:** By setting `ClientErrorMapping[StatusCodes.Status404NotFound].Link` to a custom URL.

### Q46: How do minimal APIs handle complex routes and authorization in ASP.NET Core?
**Ans:** Minimal APIs support defining complex routes and applying authorization through middleware and route handlers, similar to controller-based APIs.

### Q47: What does the `[ApiController]` attribute infer for `IFormFile` and `IFormFileCollection` parameters?
**Ans:** It infers that the `multipart/form-data` request content type should be used.

### Q48: How can you disable the default behavior of inferring `multipart/form-data` for `IFormFile` parameters?
**Ans:** By setting `SuppressConsumesConstraintForFormFileParameters` to `true` in `ApiBehaviorOptions`.

### Q49: What property disables automatic inference of parameter binding sources in ASP.NET Core?
**Ans:** `SuppressInferBindingSourcesForParameters`.

### Q50: What property disables automatic model validation error responses in ASP.NET Core APIs?
**Ans:** `SuppressModelStateInvalidFilter`.

### Q51: How do you map a custom link for a 404 status code in ASP.NET Core?
**Ans:** By setting `ClientErrorMapping[StatusCodes.Status404NotFound].Link` to a custom URL.

### Q52: What type does MVC return for an error status code 400 or higher?
**Ans:** `ProblemDetails` based on RFC 7807 specification.

### Q53: What HTTP status code does `NotFound()` return?
**Ans:** It returns a 404 status code.

### Q54: What type of response body does the `NotFound()` method generate?
**Ans:** It generates a `ProblemDetails` body in the response.

### Q55: How do you disable automatic `ProblemDetails` creation for error status codes?
**Ans:** By setting `SuppressMapClientErrors` to `true` in `ApiBehaviorOptions`.

### Q56: What attribute allows an action or controller to specify supported request content types?
**Ans:** The `[Consumes]` attribute.

### Q57: What happens if a request with a content type not supported by an action is received?
**Ans:** A 415 Unsupported Media Type response is returned.

### Q58: How do you limit an action to only handle `application/xml` content types?
**Ans:** By applying the `[Consumes("application/xml")]` attribute to the action.

### Q59: What status code is returned if a request does not specify the correct content type required by the `[Consumes]` attribute?
**Ans:** A 415 Unsupported Media Type status code.

### Q60: How does the `[Consumes]` attribute influence request selection in ASP.NET Core?
**Ans:** It applies a type constraint based on the incoming request's content type.

### Q61: What content type is required for the `PostJson` action in the example provided?
**Ans:** `application/json`.

### Q62: What content type is required for the `PostForm` action in the provided example?
**Ans:** `application/x-www-form-urlencoded`.

### Q63: What would happen if both `PostJson` and `PostForm` actions didn’t use the `[Consumes]` attribute and shared the same route?
**Ans:** An ambiguous match exception would be thrown.

### Q64: What is the purpose of the `[Consumes]` attribute in the `ConsumesController` example?
**Ans:** It allows both actions to handle the same route with different content types without causing a route conflict.

### Q65: What is the URL route for both `PostJson` and `PostForm` in the `ConsumesController` example?
**Ans:** They both handle requests sent to `https://localhost:5001/api/Consumes`.

### Q66: How does the `[Consumes]` attribute prevent ambiguous matches between actions in ASP.NET Core?
**Ans:** By applying a type constraint based on the request's content type, ensuring each action handles only its specified content type.
### Q67: What are the four primary controller action return types in ASP.NET Core?
**Ans:** Specific type, `IActionResult`, `ActionResult<T>`, and `HttpResults`.

### Q68: When is it most appropriate to use a specific type as a return type in ASP.NET Core?
**Ans:** When the action returns a primitive or complex data type and no multiple return types or error handling is required.

### Q69: What is an example of a specific return type in ASP.NET Core?
**Ans:** `Task<List<Product>>` is a specific return type for returning a collection of `Product` objects.

### Q70: When should `IActionResult` or `ActionResult<T>` be used in controller actions?
**Ans:** When multiple return types, such as different HTTP status codes, are possible.

### Q71: Why is returning `IEnumerable<T>` not always recommended in ASP.NET Core?
**Ans:** ASP.NET Core buffers the result of actions returning `IEnumerable<T>` before writing them to the response.

### Q72: What is the benefit of using `IAsyncEnumerable<T>` instead of `IEnumerable<T>` in ASP.NET Core?
**Ans:** `IAsyncEnumerable<T>` ensures asynchronous iteration, preventing buffering and improving performance.

### Q73: How does `System.Text.Json` handle the result of actions returning `IEnumerable<T>`?
**Ans:** It supports streaming the result instead of buffering it.

---

### `IActionResult` and `ActionResult<T>`

### Q74: What is `IActionResult` typically used for in ASP.NET Core?
**Ans:** It is used when an action can return different HTTP status codes or result types.

### Q75: Give an example of a shorthand method to return a BadRequest in ASP.NET Core.
**Ans:** `return BadRequest();` is shorthand for `return new BadRequestResult();`.

### Q76: What attribute helps describe possible HTTP responses for a web API action?
**Ans:** `[ProducesResponseType]` attribute.

### Q77: In which scenarios is `[ProducesResponseType]` used?
**Ans:** When the action has multiple return types, making it necessary to specify the HTTP status codes and response types.

### Q78: What HTTP status code does the `NotFound` method return?
**Ans:** 404.

### Q79: What HTTP status code does the `Ok` method return?
**Ans:** 200.

---

### Synchronous and Asynchronous Actions

### Q80: What would a synchronous action return if a product is not found in the database?
**Ans:** A 404 status code with `NotFound()`.

### Q81: What would a synchronous action return if a product is found?
**Ans:** A 200 status code with `Ok(product)`.

### Q82: What does a 201 status code represent in ASP.NET Core?
**Ans:** The resource has been successfully created.

### Q83: What does the `CreatedAtAction` method do in an action?
**Ans:** It returns a 201 status code and includes the location of the newly created resource.

### Q84: In the asynchronous action example, what happens if a product's description contains "XYZ Widget"?
**Ans:** The action returns a 400 status code with `BadRequest()`.

### Q85: How does ASP.NET Core handle model validation errors in actions with the `[ApiController]` attribute?
**Ans:** It automatically returns a 400 status code for model validation failures.

---

### `ActionResult<T>` vs `IActionResult`

### Q86: What is a key advantage of using `ActionResult<T>` over `IActionResult`?
**Ans:** The `[ProducesResponseType]` attribute's `Type` property can be excluded, simplifying the response metadata.

### Q87: Why does `ActionResult<T>` offer better type inference than `IActionResult`?
**Ans:** Because of implicit cast operators that support the conversion of both `T` and `ActionResult` to `ActionResult<T>`.

### Q88: What happens if an action returns `IEnumerable<T>` in combination with `ActionResult<T>`?
**Ans:** Conversion to a concrete type like `List<T>` is required to use `ActionResult<T>`.

### Q89: What status codes are returned in a synchronous action with `ActionResult<Product>` if the product is found or not found?
**Ans:** 200 if the product is found, 404 if the product is not found.

### Q90: What are the two possible return types in the asynchronous action with `ActionResult<Product>`?
**Ans:** A 201 status code for a created product and a 400 status code for a bad request.

---

### `HttpResults` and `IResult`

### Q91: What are `HttpResults` in ASP.NET Core?
**Ans:** They are a result implementation processed by `IResult.ExecuteAsync`, used in both Minimal APIs and Web APIs.

### Q92: How do `HttpResults` differ from MVC-specific result types?
**Ans:** They don’t leverage configured formatters or support content negotiation.

### Q93: What is the role of the `IResult` interface in ASP.NET Core?
**Ans:** It defines a contract representing the result of an HTTP endpoint.

### Q94: What does the `Results.Ok<T>()` method return in an action?
**Ans:** A 200 status code with the corresponding object in the response body.

### Q95: What method is used to return a 404 status code using `IResult`?
**Ans:** `Results.NotFound()`.

### Q96: What advantage do `Results<TResult1, TResultN>` union types offer in ASP.NET Core?
**Ans:** They automatically retain endpoint metadata and provide compile-time checking for declared return types.
