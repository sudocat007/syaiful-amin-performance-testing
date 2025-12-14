# syaiful-amin-performance-testing
syaiful amin performance testing
 

BACHELOR OF COMPUTER SCIENCE (HONS.) COMPUTER NETWORKS (CS255)


ITT440 – NETWORK PROGRAMING INDIVIDUAL ASSIGNMENT
Title: Comprehensive Web Application Performance Testing & Analysis GROUP: NBCS2555A

PREPARED BY:


NAME	STUDENT ID
SYAIFUL AMIN BIN FAUZEY	2023294246









PREPARED FOR:
SIR SHAHADAN BIN SAAD

SUBMISSION DATE:
14 December 2025
 
Table of Contents
Introduction	3
Overview of Apache JMeter	4
Test Environment and Web Target Application	5
Test Scenarios	6
Stres Test………………………………………………………………………………………..6-8
Load Test……………………………………………………………………………………..9--11
Soak Test	11-12
Analysis of Performance Data	12
Hypothesis	13
Identified Bottlenecks	14
Recommendations and improvements	15
Conclusion	16
 
Introduction

As web applications continue to support a growing number of users and services, performance and reliability have become essential factors in determining overall system quality. Users expect applications to remain responsive and stable even during peak usage periods. Performance testing is therefore an important activity in the software development lifecycle, as it helps identify weaknesses that may not be visible during functional testing.
This assignment presents a comprehensive performance testing study conducted using Apache JMeter. The chosen target for this study is the BlazeMeter Product Demos website (https://www.blazemeter.com/product-demos), which is a publicly available platform intended for demonstrating performance testing concepts. Since the application is designed for testing purposes, it is suitable for ethical and legal performance testing.
The purpose of this project is to design, execute, and analyze multiple types of performance tests, specifically Load Testing, Stress Testing, and Soak Testing. The results obtained from these tests will be evaluated using key performance indicators (KPIs) such as response time, throughput, error rate, and system resource usage. Based on the findings, potential performance bottlenecks and improvement areas will be identified and discussed.
. 
Overview of Apache JMeter

Apache JMeter is an open-source performance testing tool developed by the Apache Software Foundation. It is commonly used to test the performance, scalability, and reliability of web applications and APIs. JMeter works by simulating multiple virtual users who send requests to a target system and record how the system responds under different load conditions. JMeter is selected for this project due to its wide industry adoption, strong community support, and ability to create flexible and realistic test scenarios. It supports HTTP and HTTPS protocols and provides built-in listeners and reporting tools that make performance data analysis more manageable. These features make JMeter suitable for executing various performance testing techniques required in this assignment.























Target Application: BlazeMeter Product Demos

The BlazeMeter Product Demos website (https://www.blazemeter.com/product-demos) is selected as the target application because it is publicly accessible and specifically designed to demonstrate performance testing scenarios. The website includes interactive components and realistic user flows, making it suitable for simulating real-world user behavior. Using this application ensures that the performance tests are conducted ethically while still producing meaningful and reliable performance data.

Load testing 
is a type of performance testing used to check how a system behaves under normal and expected user traffic. It helps determine whether the application can handle the usual number of users while maintaining acceptable response times and stable performance.

Stress testing 
is performed to evaluate how a system behaves when it is pushed beyond its normal capacity limits. The purpose of stress testing is to identify the breaking point of the system, observe failures, and understand how the application responds under extreme load conditions.

Soak testing
also known as endurance testing, is used to assess the stability of an application over a long period of time under a steady load. This type of testing helps identify long-term issues such as memory leaks, performance degradation, or resource exhaustion that may not appear during short test runs.
 
Test Scenarios: 

Stress test
The performance test was carried out using Apache JMeter with a thread group configured to run 100 virtual users, a ramp-up period of 10 seconds, and a loop count of one. This configuration allowed users to be introduced gradually while simulating concurrent access to the BlazeMeter Product Demos page. The test was set to continue running even if a sampler error occurred, ensuring that the test execution was not interrupted.
According to the summary report, a total of 300 samples were recorded during the test, and all requests were completed successfully, resulting in an error rate of 0 percent. This indicates that the application remained stable under the applied load. The average response time was measured at 92 milliseconds, with the fastest request completing in 38 milliseconds and the slowest reaching 979 milliseconds. While most responses were relatively fast, the high maximum value suggests that a small number of requests experienced noticeable delays. This variation is reflected in the standard deviation value of 150.91 milliseconds.
The throughput observed during the test was approximately 2.4 requests per second, showing that the system was able to handle incoming requests at a consistent rate throughout the test duration. The response time graph also shows a brief increase in response time during the early phase of the test, followed by a more stable pattern as the load settled.
Overall, the results from the summary report indicate that the application handled the configured load effectively without any request failures. However, the presence of occasional response time spikes suggests that performance may begin to degrade if the number of concurrent users is increased further
. 
Figure 1 http request
 
Figure 2 Response Time Graph for interval 100 ms


 
Figure 3 summary report

 
Figure 4 Result

 
Figure 5 result tree







 


Load Test

This load test was conducted using Apache JMeter to evaluate the application’s performance under normal and expected user traffic. The results were analyzed mainly using the Summary Report, along with the Response Time Graph and View Results in Table.
According to the Summary Report, a total of 200 samples were executed during the load test, and all HTTP requests were completed successfully with an error rate of 0 percent. This indicates that the application remained stable and handled the expected load without any request failures. The average response time recorded was 58 milliseconds, with a minimum response time of 37 milliseconds and a maximum of 135 milliseconds, showing that most requests were processed quickly and consistently.
The standard deviation of 15.60 milliseconds suggests low variation in response times, which indicates stable performance throughout the test. The throughput during the load test was approximately 1.5 requests per second, demonstrating that the system was able to handle incoming requests at a steady rate under normal load conditions.
The Response Time Graph further supports these findings, showing mostly stable response times with only minor spikes that remained within an acceptable range. Data from the View Results in Table confirms that all requests returned successful responses.
Overall, the load testing results show that the application performs well under expected user load, maintaining low response times, consistent throughput, and zero errors. This indicates that the system is capable of supporting normal usage conditions effectively.
 
Figure 5 Load Test Thread group



 
Figure 6 http request

 
Figure 7 http request

 
Figure 8 time graph
 
Figure 9 result

 
Figure 10 result tree

 
Soak Test

The load test was successfully executed using Apache JMeter to evaluate the application’s performance under normal user load. Based on the Summary Report, a total of 200 HTTP requests were sent during the test, and all requests were completed successfully, resulting in an error rate of 0 percent. This shows that the application remained stable throughout the test execution.The average response time recorded was 80 milliseconds, with a minimum response time of 46 milliseconds and a maximum of 262 milliseconds. Most requests were processed quickly, although a few experienced higher response times, as reflected by the standard deviation of 33.97 milliseconds. This indicates moderate variation but still acceptable performance for a load test scenario.The application achieved a throughput of approximately 1.7 requests per second, showing that it was able to handle incoming requests consistently under the applied load. The Response Time Graph further confirms this behavior, showing mostly stable response times with occasional spikes that remained within a reasonable range.Overall, the load test results indicate that the application can handle expected user traffic effectively, maintaining stable performance, consistent throughput, and zero request failures.
 
Figure 11  http request


 
Figure 11  summary report 
 
Figure 12 time graph

 
Figure 13 result tree


 
Analysis of Performance Data

 




 
Hypothesis

It is expected that the web application will perform consistently under normal and expected user load, maintaining low response times, steady throughput, and no request failures during load testing. As the number of concurrent users increases, some variation in response time may occur, including occasional latency spikes during peak activity. However, the application is still expected to remain responsive and stable under moderate load conditions. During extended testing such as soak testing, the system is expected to continue operating reliably over time, with only minor performance fluctuations that may indicate early signs of resource or scalability limitations rather than critical system failures. 
Identified Bottlenecks

From the performance test results, a few possible bottlenecks were observed. While the application was able to handle normal user traffic without any request failures, there were moments where response times increased noticeably. These delays became more apparent as the number of concurrent users grew, suggesting that the system may struggle to maintain consistent performance at higher loads.
Some tests also recorded unusually high maximum response times, which may indicate limits in server processing power or delays in handling incoming requests during peak usage. The variation in response times, shown by higher standard deviation values, further suggests that request processing was not always consistent when the system was under pressure.
Although overall throughput remained stable during the tests, the presence of response time spikes shows that performance could degrade if the load continues to increase or is maintained for a long period. These findings point to potential resource-related constraints, such as CPU, memory, or request handling efficiency, rather than critical application failures.
 
Recommendations and improvements

Based on the outcomes of the load and soak tests, several improvements can be suggested to strengthen the application’s performance and long-term reliability. Although the system handled normal user traffic well and recorded no request failures, occasional increases in response time indicate that performance could be affected when the load becomes heavier or is sustained for a longer duration.
One possible improvement is to optimize backend processing to ensure requests are handled more efficiently. This may include refining application logic, reducing unnecessary processing, and improving database query performance. Introducing caching where appropriate could also help reduce response times and limit performance variation during peak usage.
Scalability should also be considered to better support increasing or prolonged user activity. Implementing horizontal scaling or autoscaling mechanisms would allow system resources to adjust dynamically based on demand, helping to maintain consistent performance during extended testing periods such as soak tests.
In addition, reviewing server resource usage, including CPU and memory consumption, could help address the response time fluctuations observed during testing. Adjusting connection handling and timeout settings may further improve responsiveness when the system is under continuous load.
Finally, continuous monitoring of key performance metrics such as response time, throughput, and resource utilization is recommended. Monitoring over longer periods would make it easier to detect early signs of performance degradation and take corrective action before users are affected.
Overall, while the application currently performs well under expected conditions, these improvements would help ensure better stability, scalability, and performance consistency in more demanding usage scenarios.
 
Conclusion
In conclusion, the performance testing conducted using Apache JMeter provided valuable insight into the application’s behavior under different load conditions. The load test results showed that the application was able to handle normal and expected user traffic efficiently, maintaining low response times, stable throughput, and zero request failures. This indicates that the system is suitable for regular usage scenarios.
Further testing also highlighted how the application behaves when subjected to higher and longer-lasting loads. While the system remained operational and stable during extended execution, occasional response time spikes were observed, suggesting potential limitations in resource handling when the load is increased or sustained. These findings help identify areas where performance could be improved to ensure better consistency.
Overall, the test results confirm that the application performs reliably under normal conditions but would benefit from optimization and scalability improvements to support heavier or long-term usage. By applying the recommended enhancements and continuing performance monitoring, the system can achieve improved stability, scalability, and user experience in real-world environments.

