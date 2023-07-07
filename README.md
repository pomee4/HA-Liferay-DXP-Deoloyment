# HA-Liferay-DXP-Deployment

Reproduction steps:

Starting the docker-compose.yml results in 2 liferay containers and 1 nginx container.
The nginx container reaches out to the mounted home folder's nginx.conf file, what handles the incoming traffic's distribution to the nodes.
![image](https://github.com/pomee4/HA-Liferay-DXP-Deoloyment/assets/13985863/51625b06-3d24-4112-b470-ea23d7fca25f)

After startup, We can access the liferay home page with http://localhost:80 from a browser.
The site at the bottom displays the active node's container ID (and the liferay port in use).:
![image](https://github.com/pomee4/HA-Liferay-DXP-Deoloyment/assets/13985863/caff1bf2-aa26-4bb5-8d13-c990094b11a7)

If we shut down the currently active node's container, and refresh the site, we can observe, that the ID has now changed to the other container's ID.:
![image](https://github.com/pomee4/HA-Liferay-DXP-Deoloyment/assets/13985863/ea897647-a655-45af-bf7d-e28271f3382b)


By clicking on the 'Sign in" button, you can observe the log in pop-up while either node is in use.:
![image](https://github.com/pomee4/HA-Liferay-DXP-Deoloyment/assets/13985863/b37f787c-ffce-4d08-9873-fa66cd966473)

Repeatedly refreshing the page results in the active node changing, but it does not occur every time.
