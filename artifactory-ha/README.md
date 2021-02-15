```bash
helm upgrade --install artifactory-ha --namespace jfrog center/jfrog/artifactory-ha \                      
--set artifactory.joinKey="edf2019bc0d330a3f058b4662b16eb7a" \   
--set artifactory.masterKey="c601841ee4a874161d9fc596a6a1974c99970771c6139eae20898eed1c61ace3" \   
--set artifactory.persistence.size=20Gi \                                                       
--set artifactory.license.secret=artifactory-cluster-license,artifactory.license.dataKey=art.lic -f values.yaml
```
