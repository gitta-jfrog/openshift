

```bash
helm upgrade --install xray --namespace jfrog center/jfrog/xray \                
--set xray.joinKey="edf2019bc0d330a3f058b4662b16eb7a" \
--set xray.masterKey="c601841ee4a874161d9fc596a6a1974c99970771c6139eae20898eed1c61ace3" \
--set xray.jfrogUrl="http://artifactory-ha-nginx.jfrog.svc.cluster.local" \
--set common.persistence.size=25Gi \
--set rabbitmq.auth.password="1WcseEOS4s" \
--set databaseUpgradeReady=true \
--set unifiedUpgradeAllowed=true -f values.yaml
```
