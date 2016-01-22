# OneRASP Agent's Docker
The Docker Image can help you quickly using OneRASP Agent to protect your application layer

## What is OneRASP？
Do you know there is 80% of attacks happening at application layer? OneRASP is  an Application Layer Protector which is RASP-based technology, enables applications to protect themselves by identifying and blocking attacks in real time.
Java version has been published, and PHP/.Net is being tested.
[click to learn more](https://www.oneasp.com/rasp/index.html)
## what is RASP
RASP is a Gartner-branded acronym for Runtime Application Self-Protection. It's built into an application and can detect and then prevent real-time application attacks. Unlike WAFs, which rely solely on network data to work and can’t see how traffic is being processed in applications. RASP leverages the application’s intrinsic knowledge of itself to accurately differentiate attacks from legitimate traffic, stopping only malicious traffic.

## How to use this image
### Start Tomcat instance with OneRASP agent
Starting a Tomcat instance is simple:

```
docker run -d -e AGENT_ID=<my_agent_id> -v <your_application_path>:/usr/local/tomcat/webapps --name=my-web oneasp/agent:tag
```

.. where my-web is the name you want to assign to your container, my_agent_id is the agent license which you can get it in [offical website](https://rasp.oneasp.com), your_application_path is your local tomcat path,See the list above for relevant tags.

### Container shell access and viewing Tomcat logs
The `docker exec` command allows you to run commands inside a Docker container. The following command line will give you a bash shell inside your tomcat container:
```
$ docker exec -it my-web bash
```
### The Tomcat Server log is available through Docker's container log:
```
$ docker logs my-web
```
