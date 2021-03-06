## Deploy ReportPortal

Deploy ReportPortal using docker-compose. 
Example of compose descriptor can be found [here](<https://github.com/reportportal/reportportal/blob/master/docker-compose.yml>)
Start application using the following command:

```powershell
docker-compose -p reportportal up -d --force-recreate
``` 

Where:
- **-p reportportal** adds prefix 'reportportal' to all containers
- **up** creates and starts containers
- **-d** daemon mode
- **--force-recreate** Re-creates containers if there any

**Useful commands:**
- **docker-compose logs** shows logs from all containers
- **docker logs &lt;container_name&gt;** shows logs from selected container
- **docker ps -a | grep "reportportal_" | awk '{print $1}' | xargs docker rm -f** Deletes all ReportPortal containers

**ReportPortal consists of the following services:**

- Redis. Used for distributed cache.
- Authorization Service. In charge of access tokens distribution.
- Gateway Service. Main entry point to application. Port used by gateway should be opened and accessible from outside network.
- API Service. Main application API.
- UI Service. All statics for user interface.
- JIRA Service. Interaction with JIRA.
- Rally Service. Interaction with Rally.
- TFS Service. Interaction with TFS.
