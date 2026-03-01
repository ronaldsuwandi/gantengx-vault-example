By default rancher-desktop vm disk usage is set to 100GB. Even when clearing docker image the size will still be reserved and no simple way of setting the size in the UI for mac

Currently it can be done by recreating the VM following this steps

- Stop Rancher Desktop
- Create an `override.yaml` file with the desired disk size, e.g.
```
echo 'disk: "30GiB"' > ~/Library/Application\ Support/rancher-desktop/lima/_config/override.yaml
```

- Delete the existing VM
```
rm -rf ~/Library/Application\ Support/rancher-desktop/lima/0
```
- Start Rancher Desktop again

## References
- https://github.com/rancher-sandbox/rancher-desktop/issues/1521#issuecomment-1030886234