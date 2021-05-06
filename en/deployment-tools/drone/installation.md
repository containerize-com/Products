---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Installing using Ubuntu

First, Install the latest version of Docker..

 ```
curl -L https://get.docker.com | bash
```

Add the current user into the docker group.

 ```
sudo usermod -aG docker $USER'
```

Run below command to ensure the docker installation.

 ```
docker --version
```

Create GitHub application by login into your account. Navigate to Settings -&gt; Developer Settings -&gt; oAuth Applications. Click on the New OAuth App button. Fill the form with required information and press Register Application button.

Copy Client ID and Client Secret. You need them in coming steps.

Download the latest available version of Drone.

 ```
docker pull drone/drone:1
```

Execute the below command to create new environment file.

 ```
sudo nano /var/drone.env
```

Copy the following configuration code and paste in editor. Replace values with the actual ones.

 ```

DRONE_GITHUB_SERVER=https://github.com
DRONE_GITHUB_CLIENT_ID=xxxxxxxxxxxx
DRONE_GITHUB_CLIENT_SECRET=xxxxxxxxxxxxxx
DRONE_RUNNER_CAPACITY=2
DRONE_SERVER_HOST=http://example.com
DRONE_SERVER_PROTO=http

```

Run command to start Drone.

 ```

docker run \
  --volume=/var/run/docker.sock:/var/run/docker.sock \
  --volume=/var/lib/drone:/data \
  --env-file=/var/drone.env \
  --publish=80:80 \
  --publish=443:443 \
  --restart=always \
  --detach=true \
  --name=drone \
  drone/drone:1

```

Open the site http://your\_server\_ip\_or\_domain.

