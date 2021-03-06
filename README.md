# kraken

A free Ceph dashboard for stats and monitoring

You can see what the latest version looks like [here](http://i.imgur.com/yhJaWXo.png)

Come hang out with us on freenode in #kraken-dashboard

Contributors:
* [Donald Talton](https://github.com/dontalton)
* [David Moreau Simard](https://github.com/dmsimard/)
* [Aaron Bassett](https://github.com/magicrobotmonkey)

## Installation and Roadmap

### Prerequisites:

The ceph-rest-api must be run on either a member of your Ceph cluster, or on a installed client node that has admin access to the cluster.


### Installation:

Create a new user called kraken then:
```
  cd /home/kraken
  git clone https://github.com/krakendash/krakendash
```

Install Kraken's dependencies:
```
apt-get install python-pip python-dev libxml2-dev libxslt-dev
pip install -r requirements.txt
```

In the krakendash/contrib directory there are two files, api.sh and django.sh

```
cp krakendash/contrib/*.sh .
```

api.sh starts the ceph-rest-api in a screen session called api
django.sh starts krakendash in a screen session called django

You can run these files to kick off the api and application. To detach a screen session, use CTRL-A, then his the D key.

Now you can run Kraken!

in /home/kraken do:
./api.sh (if you are running kraken on a ceph client or cluster node)
./django.sh
  
  
Edit krakendash/kraken/kraken/settings.py

Here you can change CEPH_BASE_URL to point at your host running ceph-rest-api, it is preconfigured already for localhost.

## Phase One
- [x] Cluster status
- [] List pools, size
- [] Pool status
- [x] Cluster data usage
- [x] MON status
- [x] OSD status
- [x] PG status

## Phase Two
- [] Advanced metrics
- [] Better graphs
- [x] Multi-MON support
- [] Better UI
- [x] Migrate from requests to [python-cephclient](https://github.com/dmsimard/python-cephclient/)

## Phase Three
- [] Modify OSD
- [] Modify MON
- [] Modify CRUSH
- [] Delete pool

### Phase Four
- [] Collectd integration
- [] Graphite integration

### Phase Five
- [] Auth system
- [] User session tracking

### Phase Six
- [] Multi-cluster support
