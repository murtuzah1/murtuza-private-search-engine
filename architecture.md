# Architecture â€” Murtuza Private Search Engine



## Overview



Murtuza Private Search Engine is a locally hosted metasearch engine built with SearXNG and Docker. It provides a customized search interface that collects search results from supported search engines and presents them in one place.



## Architecture Components



### 1. User Interface

The user opens the search engine in a web browser at `http://localhost:8080`. The interface displays the custom instance name and search results.



### 2. Docker Container

Docker runs the SearXNG application in an isolated container. This simplifies application startup and separates the application environment from the Windows host.



### 3. SearXNG

SearXNG receives search queries, requests results from configured search engines, and combines the responses into a results page.



### 4. Configuration

The local configuration file is stored at `C:\\searxng\\settings.yml`. It contains instance settings, including the custom name and server configuration. This file is kept outside the public portfolio repository to avoid exposing sensitive settings.



### 5. Local Access

Docker maps port `8080` on the host to port `8080` in the container, allowing the application to be accessed through `http://localhost:8080`.



## Request Flow



1\. The user enters a search query in the browser.

2\. The browser sends the query to the local SearXNG instance.

3\. SearXNG requests results from its configured search engines.

4\. SearXNG combines the available results.

5\. The browser displays the results to the user.



## Privacy and Security Considerations



\- The application runs locally on the user's computer.

\- The local configuration file is not included in the public repository.

\- Secret keys and other sensitive values must never be published.

\- Search requests may be sent to external search providers, depending on the configuration. Local hosting does not guarantee complete anonymity.



## Current Limitations



\- The instance is accessible locally and is not publicly deployed.

\- Search results depend on the availability and configuration of external search engines.

\- Some search engines may fail or time out.



## Future Improvements



\- Add a documented setup process.

\- Add screenshots and a demonstration.

\- Improve error handling and search-engine configuration.

\- Explore secure deployment options.



\---

\*\*Project:\*\* Murtuza Private Search Engine  

\*\*Technology:\*\* SearXNG, Docker, YAML, Windows


