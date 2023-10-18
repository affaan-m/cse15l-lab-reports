# Detailed Insights on SSH, Web Server Operations, and Networking

<img width="616" alt="Screen Shot 2023-10-18 at 2 56 03 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/ac93d817-de28-449b-bea3-f46b17815da6">

## Observations Post Login

Upon successfully logging in via SSH, I was greeted with a slew of system statistics, including CPU utilization and cluster status. Given that the system was running on ieng6, I could ascertain the server's architecture and operational status, critical for scaling the system in the future. 

<img width="630" alt="Screen Shot 2023-10-18 at 2 57 38 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/0f52bf3a-03fb-4bee-9455-58dad6f4df91">

## Code Inspection

After a meticulous code review, I noted that the HTTP server performed operations to increment an integer variable, `num`. The `Handler` class served as a URL Handler, a vital component in RESTful web services. A URL Handler processes incoming HTTP requests and routes them to specific paths, executing the corresponding logic.

### Open Questions
While I initially had no questions, given the task's complexity and possible extensions, I began to wonder: How can we optimize the URL Handler for high-throughput scenarios? Are there caching mechanisms that could be implemented to serve frequent requests faster?

## Testing "/increment"

The `/increment` path executed as expected, incrementing the `num` variable. This signifies that the server is stateful; it maintains the state of `num` across different HTTP requests.

<img width="623" alt="Screen Shot 2023-10-18 at 3 00 38 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/ddddb98f-4553-43e1-86be-2bf327ed9639">

## Testing "/add"

On invoking `/add`, the server required additional parameters, proving that the server could handle query parameters effectively. It showcases the URL Handler's ability to route and process requests based on both the path and the query parameters.

<img width="623" alt="Screen Shot 2023-10-18 at 3 01 37 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/7bcb0a51-c261-43c1-89d2-f1ec66b997ef">

## Adding Personal Touch

After inserting my name into the code and restarting the server, I noticed that using `/increment` now displayed my name along with the incremented number. This reflects that the server dynamically processes the code, thereby allowing for real-time updates.

<img width="623" alt="Screen Shot 2023-10-18 at 3 04 15 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/b09b0d6c-6d53-44fc-a13f-008c85d0909d">

## Testing "add?count=5"

Using the `/add` path with the proper syntax `add?count=5` also executed flawlessly, adding 5 to the `num` variable. This demonstrated the server's ability to handle multiple types of requests.

<img width="623" alt="Screen Shot 2023-10-18 at 3 04 25 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/8b0033f3-e2b6-4ad8-8746-fd34d049ad1a">

## Revisiting via SSH on Port 7021

I logged back into a CSE computer using SSH but switched to port 7021 this time. The change in port did not affect the server's functionality, emphasizing its robustness and adaptability.

<img width="623" alt="Screen Shot 2023-10-18 at 3 04 36 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/7ed81517-abb8-4033-a345-762f3bcb325b">

## Accessing from a Personal Laptop

Connecting from my personal laptop that was on the UCSD Protected network verified the server's accessibility. This is indicative of the server's ability to handle requests from various network environments, a crucial feature for scaling.

<img width="619" alt="Screen Shot 2023-10-18 at 3 04 48 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/e6b04f03-d338-4044-8c9d-5b86336c5eba">

## Real-Time State Reflection

Multiple browsers were able to see each other's incremented numbers, but only after a refresh or navigating back to the root directory. I surmise that the number is stored in the server computer's RAM, given the real-time state reflection across different clients.

## Code Repository and Version Control

I uploaded the search engine Java file to my GitHub repository, which can be accessed [here](https://github.com/affaan-m/cse15l-lab-reports/blob/main/SearchEngine.java). The absence of my name in the number display on the server was because I cloned the original repository, not the one with my modifications. This indicates the importance of version control and code synchronization across different environments.

## CURL Testing

I tested the server using the `curl` command both on the local machine and on the server. The seamless execution in both scenarios highlighted the server's consistency and reliability.

<img width="627" alt="Screen Shot 2023-10-18 at 3 05 01 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/1c9f55f3-2018-4af3-ab63-21c384789288">

## Thoughts

Given the server's current setup, how can we ensure that it remains fault-tolerant as we scale? What load balancing strategies can we implement to distribute incoming HTTP requests efficiently across multiple servers?
