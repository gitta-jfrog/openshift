



```bash
helm fetch center/jfrog/mission-control --untar 
```

edit templates/mission-control-statefulset.yaml

Remove the line under "prepare-storage" initContainers:
```yaml
chown -R {{ .Values.common.uid }}:{{ .Values.common.gid }} {{ .Values.missionControl.persistence.mountPath }}
```

Run Helm chart with local chart after edit the template:

```bash
 helm upgrade --install mission-control  --namespace jfrog mission-control/ \     
--set missionControl.joinKey="edf2019bc0d330a3f058b4662b16eb7a" \
--set missionControl.masterKey="c601841ee4a874161d9fc596a6a1974c99970771c6139eae20898eed1c61ace3" \
--set missionControl.jfrogUrl="http://artifactory-ha-nginx.jfrog.svc.cluster.local" \
--set unifiedUpgradeAllowed=true --set missionControl.persistence.size=20Gi  -f values.yaml
```
