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
	- ECS / NGINX / CONSUL
	- RDS

### Services / APIs
* Authentication
	* Key if the technology is ever going to work for more users
* Location (whereis.zaquesion.io)
	- Display my current location
	- Generate temp links to expose location
* Money
	* Text me balance

### Integration / 3rd Party
* Bring 3rd party data into and out of the system
	- For push systems a simple proxy could do (think bb_proxy -> current)
	- For pull systems periodic tasks orchestrated by some kind of scheduler
		- job system (iron.io, lambda, ec)
		- cron / cronos
* System for running said integrations

### Monitoring
* Tools
	* Dataloop
		- Prometheus (services)
		- statsd or influxdb (tasks)
	* Pingdom
	* twilio
* host metrics
	- cpu_user
	- bytes in/out
	* memory
	* disk
* service metrics
	- 50/90/99 Response Latency
	* Request count
	* 400s
	* 500s
* application metrics
	* db reads/writes

