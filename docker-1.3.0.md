# Docker - 1.3.0


### docker create:
docker create -[a]ttach= -[c]pu-shares= -[c]ap-add= -[e]nv="VAR=VAL" \
    -[h]ostname="" -[i]nteractive=false -[m]emory=1024{b,k,m,g} \
    --name="name" --net={'bridge','none','container','host'} \
    -[P]ublish-all=false -[p]ublish=$IP:$HPORT:$CPORT \
    -[p]rivileged=false -[r]estart={'no','on-failure[:max-retry]','always'} \
    -[t]ty=false -[u]ser="username" -[v]olume=/host:/container \
    --volumes-from=container -[w]orkdir="/some/dir" \
    --add-host=host:ip --cidfile="/write/cid/to/file" \
    --device=/dev/sdc --entrypoint="/bin/bash" \
    --env-file=default.envar --expose=8080 --link=name:alias \
    --lxc-conf="lxc.cgroup.cpuset.cpus = 0,1" --cpu-set="0-4" \
    --dns-search=search.domain.tld --dns=8.8.8.8,8.8.4.4 \
    $CONTAINER $COMMAND [$ARGS]

### docker run
...
docker run --rm=false --sig-proxy=true \
    --security-opt="label:{user,role,type,level,disable}:VALUE" \
    $CONTAINER $COMMAND [$ARGS...]
______________________________________________________________________________
External volumes with SELinux: run;
   # chcon -Rt svirt_sandbox_file_t /var/db

### docker exec
docker exec -[d]etach=false -[i]nteractive=false -[t]ty=false $CONTAINER $COMMAND [$ARGS...]

#### docker export/save
docker export container-name > container-name.tar

#### docker ps
docker ps -[a]ll=false --before=BEFORE -[f]ilter=[FILTERS] -[l]atest=false -n=-1 --no-trunc=false \
    -[q]uiet=false  -[s]ize=true --since={'id','name'}

#### docker pull
docker pull -[a]ll-tags=false NAME[:TAG]

#### docker login
docker login -[e]mail=EMAIL -[p]assword=PASSWORD -[u]sername=USERNAME

#### docker search
docker search --automated=false --no-trunc=false -[s]tars=0 TERM
