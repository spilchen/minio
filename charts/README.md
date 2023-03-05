Here are the steps on how to publish a new version of a chart

1. Make changes to the chart.
2. Commit above changes and push to github
3. cd charts/ directory
4. helm package minio-tenant   # Replace with whatever chart was updated
5. Create a new github release, using the tgz included in prior step
6. copy index.html from helmcharts repo to current directory
7. Run 'helm repo index'. Sub in values for the release
   helm repo index --merge index.yaml --url https://github.com/spilchen/minio/releases/download/0.0.2/ .
8. Check that index.yaml was updated correctly
9. Copy index.yaml back to the helmcharts repo
10. Commit change to helmcharts repo and push to github
