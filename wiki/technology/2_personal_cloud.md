Personal Cloud Infrastructure and Product
--

## Requirements
* Data Storage (f.iles.io)
	- Media
	- Service Data
* Thin APIs to expose/connect data (dokku.zaquesion.io)
* Means for integrating with 3rd Party services
	- Ingestion
	- Egestion
* Monitoring

## Notes
### Storage
* Media
	- Currently I have a 2TB 4Core box I'm using for media and application storage. I wanna separate the application storage.
	- Need considerably more space for media 2TB filled in a day; 8TB seems like a good place to start. System would need to be expandable
* Application
	- Since none of my services are terribly intense a small cluster of DigitalOcean hosts come to mind. There service has gotten considerably closer to ec2 in what you can do. Its also half the price and easier to use. That said cluster management would still be pretty manually as they don't have anything like ECS yet.

### Services / APIs
* Authentication
	* Key if the technology is ever going to work for more users
* Location (whereis.zaquesion.io)
	- Display my current location
	- Generate temp links to expose location
* Money
	* Text me balance

### Integration / 3rd Party
* Contract bring 3rd party data into and out of the system
	- For push systems a simple proxy could do (think bb_proxy -> current)
	- For pull systems periodic tasks orchestrated by some kind of scheduler
		- iron.io
		- lambda
* System for running said integrations

### Monitoring
* healthchecking and alerting
* host metrics
	- cpu_user
	- bytes in/out
	* memory
	* disk
* service metrics
	- 50/90/99 Response Latency
	* Request count
* application metrics

