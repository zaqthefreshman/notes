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
	- 48T 29T raid6 Powervault md1200
* Application
	- Backup to the above 
	- ECS / ALB / CONSUL
		- experimenting: swarm, kubernetes
	- RDS (aurora)

### Services / APIs
* Authentication
	* Key if the technology is ever going to work for more users
	* Should just bite the bullet and build what I need or use Auth0
* Location (whereis.zaquesion.io)
	- Display my current location
	- Generate temp links to expose location
* Money
	* Text me balance

### Integration / 3rd Party
* Bring 3rd party data into and out of the system
	- For push systems a simple proxy could do (think bb_proxy -> current)
	- For pull systems periodic tasks orchestrated by some kind of scheduler
		- lambda, ECS runTask()
			- http://codevoyagers.com/2016/06/22/cooperative-scaling-on-aws-ecs/
			- https://github.com/tmaiaroto/aegis
		- cloudwatch cron
* System for running said integrations

### Monitoring
* Tools
	* Managed: Prometheus / Grafana
	* Hosted: Datadog
		- Prometheus (services)
		- statsd (tasks)
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
