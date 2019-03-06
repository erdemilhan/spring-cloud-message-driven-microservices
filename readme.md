# Building and testing message-driven microservices using Spring Cloud Stream

Detailed description can be found here: [Building and testing message-driven microservices using Spring Cloud Stream](https://piotrminkowski.wordpress.com/2018/06/15/building-and-testing-message-driven-microservices-using-spring-cloud-stream/) 

# How to execute

Run all 3 services with "mvn spring-boot:run" command

Send the following POST request to order service:
POST: http://localhost:8090
{
	"customerId": 1,
	"productIds": [1, 3],
	"price": 3000
}

This should return an order response like following:
{
    "id": 1,
    "status": null,
    "price": 3000,
    "customerId": 1,
    "accountId": null,
    "productIds": [
        1,
        3
    ]
}

Then issue a GET request on order-service to see status:
GET: http://localhost:8090/1


Note that the order will be accepted as both account and product services will mark this order as accepted

