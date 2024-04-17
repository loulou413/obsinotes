---
Week: 
Themes: 
Lecture1: true
Lecture2: true
Exercises: false
---

  

## Notes

  

## Lecture 1
### IL09 - Internet Architecture
SP : internet service provider 
![[Pasted image 20240408094711.png|500]] 
ierarchie between isp 
ixp : internet xchange point :  connects every isp together. 
content provider acts like big isp
![[Pasted image 20240408095700.png|500]]
edge caches directly in the isp to from content providers to help user access easily. : offnet
Interconnected through a sophisticated hierarchy where content/cloud providers play an increasingly important role

## Lecture 2

### L10 - Internet Performance
	How do we reason about network performance? 
	What kind of performance does the Internet provide?
Packet loss : the fraction of packets from src to dst that are lost on the way
Packet delay : the time it takes for a packet to get from src to dst
Average throughput : the average rate at which dst receives data - in bits per second
Packet delay
Many components: transmission, propagation, queuing, processing

Bottleneck link : The link where traffic flows at the slowest rate, Could be because of the link’s transmission rate or because of queuing delay


Switch content : 

| Queues         | Forwarding table                                     |
| -------------- | ---------------------------------------------------- |
| stores packets | store meta-data - indicate where to send each packet |

2 choices : 

| Packet switching                            | (Virtual) circuit switching                          |
| ------------------------------------------- | ---------------------------------------------------- |
| packets treated on demand                   | resources reserved in advance                        |
| admission & forwarding decision: per packet | admission & forwarding decision: per virtual circuit |
