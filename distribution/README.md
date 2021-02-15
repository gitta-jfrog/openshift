```bash
helm upgrade --install distribution --namespace jfrog center/jfrog/distribution \
--set distribution.joinKey="edf2019bc0d330a3f058b4662b16eb7a" \
--set distribution.masterKey="c601841ee4a874161d9fc596a6a1974c99970771c6139eae20898eed1c61ace3" \
--set distribution.jfrogUrl="http://artifactory-ha-nginx.jfrog.svc.cluster.local" \
--set distribution.persistence.size=20Gi \
--set redis.password="1WcseEOS4s" \
--set databaseUpgradeReady=true \
--set unifiedUpgradeAllowed=true -f values.yaml
```
