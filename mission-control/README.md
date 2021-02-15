



```bash
helm fetch center/jfrog/mission-control --untar 
```

edit templates/mission-control-statefulset.yaml

Remove
```yaml
chown -R {{ .Values.common.uid }}:{{ .Values.common.gid }} {{ .Values.missionControl.persistence.mountPath }}
```
