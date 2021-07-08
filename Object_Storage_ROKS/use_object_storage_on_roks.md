# For IBM Cloud, your secret might resemble the following file:
```
apiVersion: v1
kind: Secret
metadata:
  name: thanos-object-storage
  namespace: open-cluster-management-observability
type: Opaque
stringData:
  thanos.yaml: |
    type: s3
    config:
      bucket: YOUR_S3_BUCKET
      endpoint: YOUR_S3_ENDPOINT
      insecure: true
      access_key: YOUR_ACCESS_KEY
      secret_key: YOUR_SECRET_KEY
```
You can follow the steps to create object storage in IBM Cloud:
1. Create object storage from https://cloud.ibm.com/objectstorage/create.
2. From *Resource list -> Storage* to select your created object storage.
3. Click *Create bucket* button to create your bucket. That is `YOUR_S3_BUCKET`.
4. Follow the [document](https://cloud.ibm.com/docs/cloud-object-storage/iam?topic=cloud-object-storage-service-credentials) to create service credential with HMAC enabled.
5. You can get `access_key_id` and `secret_access_key` from your service credentials. `access_key_id` is `YOUR_ACCESS_KEY` and `secret_access_key` is `YOUR_SECRET_KEY`.
6. You can get `YOUR_S3_ENDPOINT` from [endpoints](https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-endpoints#endpoints)
