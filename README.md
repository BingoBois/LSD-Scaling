# LSD-Scaling

---

Hand-in for LSD assignment 12 "Scaling"

https://github.com/datsoftlyngby/soft2018fall-lsd-teaching-material/blob/master/assignments/12-DevOps_Scaling.md
---


DevOps Repo: https://github.com/BingoBois/DolphinNewsDevOps

The team decided very early on in the development process to implement scaling capabilities to the project, and so the project has been running using Kubernetes for the past several months. At the same time, the team also successfully implemented auto deployment of new builds (rolling updates) from Github, meaning when a new build was pushed to github, the build would automatically be deployed on the Frontend and Backend. \
It's important to note however, that the team did encounter some issues regarding auto-deployment of the frontend, which was fixed when the team upgraded the hardware and found a small spelling-snaffy. But since the implementation of Kubernetes, the backend has been auto-deployed and working as expected and in general, the experience has been great.  

Setup:

1 Master Kubernetes Orchestrator (80.240.24.203) (root !sG5[apHwB?cW%r_)

1 Slave Machine (hosts pods) (108.61.211.164) (root =C3zX]Zn4}vtA1W1)



*   Master machine also hosts load balancing
*   Slave machine hosts an SQL instance on top of the pods
*   2 pods for each of the Backend and the Frontend

Learning:



*   Hard to incorporate something new into a project (and not test it out at first)
*   Long learning process, mistakes (seen in the many PR requests to fix stuff…)
*   Many hours spent trying out stuff, learning. Issue with continuous deployment still on frontend because of a "slow" droplet.
*   Had to do a weird setup, with a beta loadbalancer, and homebrew webhook scripts, since we aren't using google cloud
*   Good experience, and the best thing to take away from this project. (and definitely the newest technology we have worked with!, even though we picked it ourselves)

Technical:



*   Allows 100% uptime, rollback if something goes wrong
*   Very easy to maintain once you know basic commands, harsh learning curve in the beginning though.
*   Requires the user to be very familiar with docker.
*   Auto-deploys new builds of the Frontend and Backend from Github repos
*   Pods
    *   Originally only used 2 pods for hosting the Frontend and 2 pods for hosting the Backend
    *   When the team upgraded the Hardware hosting the Kubernetes (More RAM and the support of Auto Deployment from Github of the Frontend), we also increased the backend pods from 2 to 4

For even more details regarding our Kubernetes-setup and process, please see the link to our DevOps repo in the top of this document.
