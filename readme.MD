Epikian Technical Task
===============================

Looking to become an Epikian? It is simple read the task description, look at the diagram, create a solution using any design style, using your own practices and send us a pull request and we are going to reach back to you to have a talk.

Task description
======================

We want you to create a set of REST web services using .NET as the technology stack for the following domain:

![alt text](/Design/Domain.png "Shipping container Reuse")

The above domain diagram is related to the Shipping container reuse scenario, something which is very dear to us (and its really suitable for domain driven design modeling).

The domain is composed of the following elements:
- Actor = this is the main entity of the container domain; there are two types of Actors a carrier which provides containers for reuse and transporters who require containers. Transporters can only request containers for reuse (and pay for the privilege) while Carriers need only to reject or approve each reuse request (if its valid, otherwise its automatically rejected)
- Account - Transporter Actors have accounts with credits on. Each Reuse request will subtract a fixed amount from the Transporters account, while a top-up will increase it. We want to keep a record of it so we will log every transaction
- Container - a container is your standard shipping container. Each container can be reused only once per day otherwise the Carrier needs to decide per case basis if he wants to approved or reject the reuse request
- Reuse - the Reuse entity tracks a single container reuse request issued by a Transporter towards a Carrier for a specific Container on a specific Date. Its has a price, 25 euros and a Status (Pending, Approved or Rejected).

We want you to create the following web services:
- Actor/Create
- Transporter/AddCredits
- Transporter/RequestReuse
- Carrier/AddContainer
- Carrier/ApproveRequest
- Carrier/RejectRequest
- Reuse/ListReuseRequest

Do it any way you like, add a database or not; add unit tests or not; create a UI or not; add validation rules or more logic or not; change the domain classes or URL. You have the freedom to decide.
