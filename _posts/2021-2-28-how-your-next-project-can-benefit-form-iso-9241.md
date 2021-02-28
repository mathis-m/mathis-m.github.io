---
layout: post
title: How your next project can benefit form ISO 9241
---

Human-Computer Interaction(short HCI) is research at the interface between humans and computers using computers. If your next Project requires designing a clear intuitive system which will be usable by a broad range of people with different abilities and expertise, and who have not completed any formal training you will benefit form this research. Many of these research results are defined as the ergonomics of human-computer interaction standards in ISO 9241.

I have my next project up my mind how about you? If you have one now is the time to have a look at the user centered development lifecycle defined in [ISO 9241–210:2019](https://en.wikipedia.org/wiki/ISO_9241#ISO_9241-210):

![user-centered development process](https://cdn-images-1.medium.com/max/7218/1*Gu9Qmv5dz4bOMPN33lhitA.png)*user-centered development process*

This standard defines a cyclic development process which aims to be user-centered. Although you may be restricted to a development process of your company like SCRUM, you can have a look at the stages and methods used in this standard in order to integrate them in your process too.

## Planning the Process

First of all the goals of the project need to be defined. If your project involves multiple people they should be included in this process.
In case your project is a new project you should do research on the [market](https://en.wikipedia.org/wiki/Market_research) and possible [competitors](https://en.wikipedia.org/wiki/Competitor_analysis) in addition.

### *My Goals*

My next project will be to do an [Usability Evaluation](https://www.usability.gov/what-and-why/usability-evaluation.html) of Swagger-UI.

[Swagger-UI](https://swagger.io/tools/swagger-ui/) is one of the most useful tools when it comes to interacting with RESTful APIs. Using Swagger-UI APIs can be documented and tested without any client implementation in place. The decision of .NET 5 to enable [OpenAPI Integration by default](https://docs.microsoft.com/en-us/aspnet/core/release-notes/aspnetcore-5.0?view=aspnetcore-5.0#openapi-specification-on-by-default) when creating a new API, puts Swagger-UI in a leading position.

If you don’t know Swagger-UI you can have a look at their [PetStore Server demo](https://petstore3.swagger.io/). You will be provided a list of operations that you can expand via a click. Now you will be presented the operations documentation, it will state the operation’s parameters, request body and responses(Further reading about [Http Protocol format](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Message_format)). The Try-Out button can be used to activate the testing state, where you can execute the operation. 

![Swagger-UI demo: [https://petstore3.swagger.io/](https://petstore3.swagger.io/)](https://cdn-images-1.medium.com/max/4352/1*E-jnF9XlBseNTPztGFda6g.png)*Swagger-UI demo: [https://petstore3.swagger.io/](https://petstore3.swagger.io/)*

I am using Swagger-UI on daily basis and I experience several pain points. This is why I decided to use the standards defined in [I](https://en.wikipedia.org/wiki/ISO_9241)SO 9241 to analyze Swagger-UI. This will lead to an detailed analysis of the product and its users, in addition I will try to solve the discovered usability issues by creating a possible solution, demonstrated as a High-Fidelity Prototype, the whole process will be documented and used to create a Feature Request at GitHub.

### My Issue with UX and Swagger-UI

When interacting with larger API’s that that define many operations one have to scroll a lot. There is no way to jump to a operation through some navigation feature. The only way interact with multiple positions within Swagger-UI is to open multiple tabs in the browser for each position you want to interact with.
In addition Swagger-UI provides to main features. First documentation, second Try-Out ability. When you know the API and want to use Swagger-UI primarily for the sake of trying out the functionality of the API, one needs to do many clicks and scroll in order to get to the Try-Out mode. The in the documentation integrated Try-Out mode is too nested and slows down my workflows enormously.

[Try it yourself using the official OpenAPI Specification for ](https://petstore3.swagger.io/?url=https://raw.githubusercontent.com/github/rest-api-description/main/descriptions/api.github.com/api.github.com.yaml)[api.github.com](https://petstore3.swagger.io/?url=https://raw.githubusercontent.com/github/rest-api-description/main/descriptions/api.github.com/api.github.com.yaml)[!](https://petstore3.swagger.io/?url=https://raw.githubusercontent.com/github/rest-api-description/main/descriptions/api.github.com/api.github.com.yaml)

From my opinion Swagger-UI should implement a more flexible User-Interface that allows to build better workflows yourself. Imagine a Code editor like Visual Studio Code. If you interact with a large file and do not want to jump between multiple positions in that file. You can open the same file in another tab that is split side by side so you can view both positions at once.

I think now is the time to think about the future of Swagger-UI usability wise.

## Context of Use

The usability of software depends on the context of use. This context is defined in [ISO 9241–11](https://de.wikipedia.org/wiki/ISO_9241#ISO_9241-11_Gebrauchstauglichkeit:_Begriffe_und_Konzepte). It specifies user types mapped to goals, tasks, resources (for example hardware and software a user may use to access the product), and the physical, social, cultural, and organizational environment.

### User Groups

Let’s start defining the context of use by identifying  different user groups that will use Swagger-UI within a product’s lifecycle in order to show the different goals and tasks different users might have.  

**Product developer**  
The product developer is working on a product that leverages Swagger-UI’s documentation and testing ability. The developer may have the following task or goals:

1. **Testing within product development lifecycle**  
The developer may use Swagger-UI to test the API’s functionality.
He exactly knows what part of the API he will be interacting with and so the part of Swagger-UI he is going to interact with.

2. **Interact with the API**  
In addition the developer may use Swagger-UI to accomplish some task that requires interacting with the API. It is possible that the task requires multiple subsequent request to be run.

3. **Gathering information**  
If the developer is new to the project he may want to read the documentation of the service. In addition he wants to try out some methods to understand the API.

**Client developer**  
The client developer relies on Swagger-UI in order to gain information about an API and to test an API interface. The developer may have the following goals or is required to solve following tasks:

1. **Acquiring interface information**  
The developer may have the task to evaluate the interface provided by an API. He will use Swagger-UI’s documentation in order to know what data he needs to provide and what data he will receive. This may also include testing via the Try-Out mode.

2. **Manual testing**  
In order to test the API with default client the developer may use Swagger-UI’s Try-Out mode to test the API.

**Consultant introducing the API to client developer**  
A consultant may use Swagger-UI to introduce new client developer to the API or to present a new feature of the API to a client developer knowing the product already. In this context he may have the following tasks and goals:

1. **Showing basic documentation structure**  
When onboarding a new client developer a consultant may use the documentation to outline the different parts of the API.

2. **Demonstrate the API**  
Consultants might  use Swagger-UI to demonstrate different scenarios for interacting with the API.

**Tester**  
When testing the product a tester may rely on Swagger-UI to interact with the API. He may be given the following task:

1. **Testing valid data**  
A tester may be given some test data he needs to process through Swagger-UI.

2. **Testing invalid data**  
A tester may need to test the API with invalid inputs.

**Other Stakeholders**  
Non technical stakeholders may use Swagger-UI to archive the following tasks:

1. **Requirements check**  
A requirements manager may use Swagger-UI for testing given requirements.

2. **Health check**  
A Product Owner might use Swagger-UI to check for the API’s health.

### Workflows

The above stated interactions with Swagger-UI can be abstracted into workflows. A workflow should demonstrate a typical user interaction which is a requirement for a possible user.

1. **Read documentation**  
In case one needs to read the documentation he can either read from top to bottom or one is interested in a specific documentation part and needs to search for it.

2. **Testing single operation**  
A single operation may be easy to find, but this depends on the tag and operation count per tag.
If there are many operations per tag it is hard to find the operation that you are looking for.  
**Steps:** scroll to operation > expand operation > click Try out  
**Step Count:** 3

3. **Testing n subsequent operations**  
In case of testing n subsequent operations a developer needs to scroll a lot. Most of the time it is more efficient to close the operation then to scroll all the way down to the next operations. Another approach would be to have multiple browser tabs open at a time.  
**Steps:**  
[scroll to operation > expand operation > click Try out > collapse operation | tab switch] * (n — 1)
\+ [scroll to operation > expand operation > click Try out]  
**Step Count:** 4n — 1

1. **Read documentation and test operation**  
In case of testing an operation it may be required to jump to some documentation part like Schemas section or other operation for gathering further information. This results in lot of scrolling.

### Environment

When confronted with different environments, users may have different requirements, so it is important to note them for the user research part.

**Physical**  
The physical environment describes the physical situation that user is currently in.
Users may use Swagger-UI within their regular company environment or working environment. 

**Technical**  
The technical environment describes the underling Hardware and Software used to access the product.
One might access the Swagger-UI from a desktop or mobile device.

**Social**  
This is covers the social and psychological influences.
When having the goal to use Swagger-UI to present the API to someone, one might be stressed.

### User Research

In order to get to know the users, user research will focus on wishes, goals, expectations, requirements, behavior and motivations of the users. This user research results can be used for developing or enhancing a product or as a template and input for designers, developers. There are two ways of getting to know the user. We can either wait for the users to get active for example by providing feedback via [GitHub Issues](https://github.com/swagger-api/swagger-ui/issues). Or we can get active by observing, interviewing, testing, recording or tracking data.

#### User Research Methods
**The following methods can be used to gather more information about users:**  

**Desk Researching**  
Desk Researching will usually take place at the start of a project. The goal is to harvest secondary data or that which has already been collected. Most of the time there wont be an research that exactly matches the one you are planning to do. However, the probability is high that someone has already dealt with partial problems or similar ones you are trying to solve.  
GitHub Issue is a good place to start when it comes to Open Source related projects.  
For example there is [#6528](https://github.com/swagger-api/swagger-ui/issues/6528), there the author describes that he uses Swagger-UI mainly for trying out the API. The solution that was introduced here is the ability to configure Swagger-UI with a flag to enable the Try-Out by default([try it yourself](https://petstore.swagger.io/?tryItOutEnabled=true)). For me this feels more like a workaround then a possible solution, because it just hides the root cause of the problem: the two main features (Documentation and Try-Out) are combined in an not user-friendly way.  
In [#2805](https://github.com/swagger-api/swagger-ui/issues/2805) the author does report that the Try-Out Mode slows down and he points out that in case of wanting to view only the documentation the UI could be reduced. For example the Authorize button could be moved to a configuration section instead of being placed at the top of the documentation.  
In addition [#5264](https://github.com/swagger-api/swagger-ui/issues/5264) states how messed up the UI is, the author shows his concerns about the actual response result being not well separated from the documented responses. Actually this is a issue that I run into on common basis.  

![](https://cdn-images-1.medium.com/max/3244/1*nIDmTKDpYzEC-yrbf4Gn5A.png)

In [#4018](https://github.com/swagger-api/swagger-ui/issues/4018) it is stated that when it comes to large responses Swagger-UI freezes because of the syntax highlighting. This could be fixed by providing a toggle to switch between raw and formatted response.  
The author of [#6295](https://github.com/swagger-api/swagger-ui/issues/6295) states that if a request body includes for example an extra comma the operation can not be executed. This corresponds with the identified need of a tester that would like to test invalid data. Swagger-UI does a good job validating the request and I like that feature but some times a unrestricted mode is required.  
With [#5169](https://github.com/swagger-api/swagger-ui/issues/5169) the author shows that Swagger-UI lacks behind on it's multipart documentation feature. In multipart request the request body is split into parts. Currently when viewing multipart body in the documentation one does get no preview of a sample value. It should be documented just like the parameters part is.  
![image](https://user-images.githubusercontent.com/11584315/109387213-5d776a00-7900-11eb-8c56-161cf5bf5152.png)
In [#4735](https://github.com/swagger-api/swagger-ui/issues/4735) the need for a custom URL input is clarified. With this users are able to change the server URL on demand. Currently this would require a change of the OpenAPI Specification used.

- TODO

Further reading about the methods at [User Research manual from gov.uk](https://www.gov.uk/service-manual/user-research#default-id-8d12616e-heading-4).

### Personas

TODO

### Scenarios

TODO

### Customer Journey and Experience Map

TODO
