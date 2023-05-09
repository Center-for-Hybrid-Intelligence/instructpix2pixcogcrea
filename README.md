# instructpix2pixcogcrea
Cog repo for instructpix2pix for the crea.visions project

When the instance on lambda labs is created and the SSH key setup run on your computer:
```console
ssh -i <your-ssh-key> ubuntu@<IP> 
```
And then on the machine:
```console
git clone https://github.com/brabecq/instructpix2pixcogcrea.git

cd instructpix2pixcogcrea
chmod +x makefile.sh
./makefile.sh
```

## update the crea universe server
repository: https://github.com/Center-for-Hybrid-Intelligence/creavisions-universe

vm 7: 13.69.169.201

update the two keys `GPUCount` and `GPUNodeHost` to reflect the lambda hardware. Also set `useReplicateNodeAsReserve` if you want to add one more GPU billed by replicate.

fx.
```
GPUCount: 8,
GPUNodeHost: `https://${IP}`,
useReplicateNodeAsReserve: true
```

then push changes to github
then pull on server and follow repository instructions to deploy changes to the universe production vm:

```
// pwd = ./client
npm run build
```

```
// (background session) pwd = ./server
ctrl + c
npm run serve
ctrl + a then d
ctrl + d
ctrl + d
```


And that's it!
