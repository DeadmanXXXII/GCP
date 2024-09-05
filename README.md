# GCP
Here is a comprehensive list of Google Cloud Platform (GCP) CLI commands using `gcloud`, organized by their functionality. This list covers a variety of GCP services and operations.

# Google Cloud CLI Commands

## General Commands

- **Authenticate to Google Cloud:**
  ```bash
  gcloud auth login
  ```

- **List available projects:**
  ```bash
  gcloud projects list
  ```

- **Set the active project:**
  ```bash
  gcloud config set project PROJECT_ID
  ```

- **Get current project:**
  ```bash
  gcloud config get-value project
  ```

- **List available regions and zones:**
  ```bash
  gcloud compute regions list
  gcloud compute zones list
  ```

- **Get `gcloud` CLI version:**
  ```bash
  gcloud --version
  ```

## Compute Engine

- **List all instances:**
  ```bash
  gcloud compute instances list
  ```

- **Create a new instance:**
  ```bash
  gcloud compute instances create INSTANCE_NAME --zone=ZONE --image-family=IMAGE_FAMILY --image-project=IMAGE_PROJECT
  ```

- **Start an instance:**
  ```bash
  gcloud compute instances start INSTANCE_NAME --zone=ZONE
  ```

- **Stop an instance:**
  ```bash
  gcloud compute instances stop INSTANCE_NAME --zone=ZONE
  ```

- **Delete an instance:**
  ```bash
  gcloud compute instances delete INSTANCE_NAME --zone=ZONE --quiet
  ```

- **List available machine types:**
  ```bash
  gcloud compute machine-types list --zones=ZONE
  ```

## Cloud Storage

- **List all buckets:**
  ```bash
  gcloud storage buckets list
  ```

- **Create a new bucket:**
  ```bash
  gcloud storage buckets create BUCKET_NAME --location=LOCATION
  ```

- **Delete a bucket:**
  ```bash
  gcloud storage buckets delete BUCKET_NAME
  ```

- **List objects in a bucket:**
  ```bash
  gcloud storage objects list --bucket=BUCKET_NAME
  ```

- **Upload a file to a bucket:**
  ```bash
  gcloud storage cp LOCAL_FILE gs://BUCKET_NAME/
  ```

- **Download a file from a bucket:**
  ```bash
  gcloud storage cp gs://BUCKET_NAME/REMOTE_FILE LOCAL_FILE
  ```

## Networking

- **List all VPC networks:**
  ```bash
  gcloud compute networks list
  ```

- **Create a new VPC network:**
  ```bash
  gcloud compute networks create NETWORK_NAME --subnet-mode=auto
  ```

- **Delete a VPC network:**
  ```bash
  gcloud compute networks delete NETWORK_NAME
  ```

- **List all firewall rules:**
  ```bash
  gcloud compute firewall-rules list
  ```

- **Create a new firewall rule:**
  ```bash
  gcloud compute firewall-rules create RULE_NAME --allow tcp:80,tcp:443 --source-ranges 0.0.0.0/0 --target-tags TARGET_TAG
  ```

- **Delete a firewall rule:**
  ```bash
  gcloud compute firewall-rules delete RULE_NAME
  ```

## Cloud SQL

- **List all Cloud SQL instances:**
  ```bash
  gcloud sql instances list
  ```

- **Create a new Cloud SQL instance:**
  ```bash
  gcloud sql instances create INSTANCE_NAME --database-version=VERSION --tier=TIER --region=REGION
  ```

- **Delete a Cloud SQL instance:**
  ```bash
  gcloud sql instances delete INSTANCE_NAME
  ```

- **List databases in a Cloud SQL instance:**
  ```bash
  gcloud sql databases list --instance=INSTANCE_NAME
  ```

- **Create a new database in Cloud SQL:**
  ```bash
  gcloud sql databases create DATABASE_NAME --instance=INSTANCE_NAME
  ```

- **Delete a database from Cloud SQL:**
  ```bash
  gcloud sql databases delete DATABASE_NAME --instance=INSTANCE_NAME
  ```

## App Engine

- **List all App Engine services:**
  ```bash
  gcloud app services list
  ```

- **Deploy an App Engine application:**
  ```bash
  gcloud app deploy
  ```

- **Delete an App Engine service:**
  ```bash
  gcloud app services delete SERVICE_NAME
  ```

- **List all App Engine versions:**
  ```bash
  gcloud app versions list
  ```

- **Stop an App Engine version:**
  ```bash
  gcloud app versions stop VERSION_ID
  ```

- **Start an App Engine version:**
  ```bash
  gcloud app versions start VERSION_ID
  ```

## IAM (Identity and Access Management)

- **List all IAM roles:**
  ```bash
  gcloud iam roles list
  ```

- **Create a new IAM role:**
  ```bash
  gcloud iam roles create ROLE_NAME --title="TITLE" --permissions="PERMISSIONS" --stage="GA"
  ```

- **Delete an IAM role:**
  ```bash
  gcloud iam roles delete ROLE_NAME
  ```

- **List all IAM policies for a resource:**
  ```bash
  gcloud projects get-iam-policy PROJECT_ID
  ```

- **Set an IAM policy binding:**
  ```bash
  gcloud projects add-iam-policy-binding PROJECT_ID --member='user:EMAIL' --role='roles/ROLE'
  ```

- **Remove an IAM policy binding:**
  ```bash
  gcloud projects remove-iam-policy-binding PROJECT_ID --member='user:EMAIL' --role='roles/ROLE'
  ```

## Kubernetes Engine (GKE)

- **List all GKE clusters:**
  ```bash
  gcloud container clusters list
  ```

- **Create a new GKE cluster:**
  ```bash
  gcloud container clusters create CLUSTER_NAME --zone=ZONE
  ```

- **Delete a GKE cluster:**
  ```bash
  gcloud container clusters delete CLUSTER_NAME --zone=ZONE
  ```

- **Get credentials for a GKE cluster:**
  ```bash
  gcloud container clusters get-credentials CLUSTER_NAME --zone=ZONE
  ```

- **List all Kubernetes pods in a cluster:**
  ```bash
  kubectl get pods
  ```

## BigQuery

- **List all datasets:**
  ```bash
  bq ls
  ```

- **Create a new dataset:**
  ```bash
  bq mk DATASET_NAME
  ```

- **Delete a dataset:**
  ```bash
  bq rm -r -f DATASET_NAME
  ```

- **List tables in a dataset:**
  ```bash
  bq ls DATASET_NAME
  ```

- **Create a new table:**
  ```bash
  bq mk --table DATASET_NAME.TABLE_NAME SCHEMA
  ```

- **Delete a table:**
  ```bash
  bq rm -f DATASET_NAME.TABLE_NAME
  ```

- **Run a query:**
  ```bash
  bq query --use_legacy_sql=false 'QUERY'
  ```

## Cloud Functions

- **List all Cloud Functions:**
  ```bash
  gcloud functions list
  ```

- **Deploy a new Cloud Function:**
  ```bash
  gcloud functions deploy FUNCTION_NAME --runtime RUNTIME --trigger-http --entry-point ENTRY_POINT
  ```

- **Delete a Cloud Function:**
  ```bash
  gcloud functions delete FUNCTION_NAME
  ```

- **Invoke a Cloud Function:**
  ```bash
  gcloud functions call FUNCTION_NAME --data '{"key":"value"}'
  ```

## Cloud Pub/Sub

- **List all Pub/Sub topics:**
  ```bash
  gcloud pubsub topics list
  ```

- **Create a new Pub/Sub topic:**
  ```bash
  gcloud pubsub topics create TOPIC_NAME
  ```

- **Delete a Pub/Sub topic:**
  ```bash
  gcloud pubsub topics delete TOPIC_NAME
  ```

- **List all Pub/Sub subscriptions:**
  ```bash
  gcloud pubsub subscriptions list
  ```

- **Create a new Pub/Sub subscription:**
  ```bash
  gcloud pubsub subscriptions create SUBSCRIPTION_NAME --topic=TOPIC_NAME
  ```

- **Delete a Pub/Sub subscription:**
  ```bash
  gcloud pubsub subscriptions delete SUBSCRIPTION_NAME
  ```

## Cloud Run

- **List all Cloud Run services:**
  ```bash
  gcloud run services list
  ```

- **Deploy a new Cloud Run service:**
  ```bash
  gcloud run deploy SERVICE_NAME --image gcr.io/PROJECT_ID/IMAGE --platform managed
  ```

- **Delete a Cloud Run service:**
  ```bash
  gcloud run services delete SERVICE_NAME
  ```

## Cloud Monitoring

- **List all monitoring dashboards:**
  ```bash
  gcloud monitoring dashboards list
  ```

- **Create a new monitoring dashboard:**
  ```bash
  gcloud monitoring dashboards create --title "DASHBOARD_TITLE" --config-file "DASHBOARD_CONFIG_FILE"
  ```

- **Delete a monitoring dashboard:**
  ```bash
  gcloud monitoring dashboards delete DASHBOARD_ID
  ```

- **List all alert policies:**
  ```bash
  gcloud monitoring alert-policies list
  ```

- **Create a new alert policy:**
  ```bash
  gcloud monitoring alert-policies create --notification-channels=CHANNEL_ID --condition="CONDITION" --display-name="ALERT_POLICY_NAME"
  ```

- **Delete an alert policy:**
  ```bash
  gcloud monitoring alert-policies delete ALERT_POLICY_ID
  ```

## Cloud Logging

- **List all logs:**
  ```bash
  gcloud logging logs list
  ```

- **Read logs from a specific log:**
  ```bash
  gcloud logging read "logName=\"projects/PROJECT_ID/logs/LOG_NAME\"" --limit=LIMIT
  ```

- **Create a log-based metric:**
  ```bash
  gcloud logging metrics create METRIC_NAME --description="DESCRIPTION" --filter="FILTER_EXPRESSION"
  ```

- **Delete a log-based metric:**
  ```bash
  gcloud logging metrics delete METRIC_NAME
  ```

## Cloud Identity-Aware Proxy (IAP)

- **List all IAP-secured resources:**
  ```bash
  gcloud iap resources list
  ```

- **Get IAP policy for a resource:**
  ```bash
  gcloud iap web services describe SERVICE_NAME
  ```

- **Set IAP policy for a resource:**
  ```bash
  gcloud iap web services add-iam-policy-binding SERVICE_NAME --member='user:EMAIL' --role='roles/iap.httpsResourceAccessor'
  ```

- **Remove IAP policy for a resource:**
  ```bash
  gcloud iap web services remove-iam-policy-binding SERVICE_NAME --member='user:EMAIL' --role='roles/iap.httpsResourceAccessor'
  ```

## Cloud Build

- **List all build triggers:**
  ```bash
  gcloud builds triggers list
  ```

- **Create a new build trigger:**
  ```bash
  gcloud builds triggers create CLOUD_BUILD_TRIGGER --name=TRIGGER_NAME --repo-name=REPO_NAME --branch-pattern="BRANCH_PATTERN"
  ```

- **Delete a build trigger:**
  ```bash
  gcloud builds triggers delete TRIGGER_NAME
  ```

- **Submit a build:**
  ```bash
  gcloud builds submit --tag gcr.io/PROJECT_ID/IMAGE_NAME .
  ```

## Cloud Dataproc

- **List all Dataproc clusters:**
  ```bash
  gcloud dataproc clusters list
  ```

- **Create a new Dataproc cluster:**
  ```bash
  gcloud dataproc clusters create CLUSTER_NAME --region=REGION --zone=ZONE
  ```

- **Delete a Dataproc cluster:**
  ```bash
  gcloud dataproc clusters delete CLUSTER_NAME --region=REGION
  ```

- **Submit a Spark job to Dataproc:**
  ```bash
  gcloud dataproc jobs submit spark --cluster=CLUSTER_NAME --region=REGION --class=CLASS_NAME --jars=JAR_FILE
  ```

- **List jobs in Dataproc:**
  ```bash
  gcloud dataproc jobs list --region=REGION
  ```

- **Cancel a Dataproc job:**
  ```bash
  gcloud dataproc jobs cancel JOB_ID --region=REGION
  ```

## Cloud AI and ML

- **List all AI Platform models:**
  ```bash
  gcloud ai models list
  ```

- **Create a new AI Platform model:**
  ```bash
  gcloud ai models create MODEL_NAME
  ```

- **Delete an AI Platform model:**
  ```bash
  gcloud ai models delete MODEL_NAME
  ```

- **Deploy a version of a model:**
  ```bash
  gcloud ai versions create VERSION_NAME --model=MODEL_NAME --origin=MODEL_DIR
  ```

- **Delete a version of a model:**
  ```bash
  gcloud ai versions delete VERSION_NAME --model=MODEL_NAME
  ```

## Bigtable

- **List all Bigtable instances:**
  ```bash
  gcloud bigtable instances list
  ```

- **Create a new Bigtable instance:**
  ```bash
  gcloud bigtable instances create INSTANCE_NAME --cluster=CLUSTER_NAME --cluster-zone=ZONE --display-name="DISPLAY_NAME"
  ```

- **Delete a Bigtable instance:**
  ```bash
  gcloud bigtable instances delete INSTANCE_NAME
  ```

- **List tables in a Bigtable instance:**
  ```bash
  gcloud bigtable tables list --instance=INSTANCE_NAME
  ```

- **Create a new table in Bigtable:**
  ```bash
  gcloud bigtable tables create TABLE_NAME --instance=INSTANCE_NAME
  ```

- **Delete a table in Bigtable:**
  ```bash
  gcloud bigtable tables delete TABLE_NAME --instance=INSTANCE_NAME
  ```

## Cloud Spanner

- **List all Spanner instances:**
  ```bash
  gcloud spanner instances list
  ```

- **Create a new Spanner instance:**
  ```bash
  gcloud spanner instances create INSTANCE_NAME --config=CONFIG_NAME --display-name="DISPLAY_NAME" --nodes=NUM_NODES
  ```

- **Delete a Spanner instance:**
  ```bash
  gcloud spanner instances delete INSTANCE_NAME
  ```

- **List databases in a Spanner instance:**
  ```bash
  gcloud spanner databases list --instance=INSTANCE_NAME
  ```

- **Create a new database in Spanner:**
  ```bash
  gcloud spanner databases create DATABASE_NAME --instance=INSTANCE_NAME
  ```

- **Delete a database in Spanner:**
  ```bash
  gcloud spanner databases delete DATABASE_NAME --instance=INSTANCE_NAME
  ```

## Cloud Memorystore

- **List all Redis instances:**
  ```bash
  gcloud redis instances list
  ```

- **Create a new Redis instance:**
  ```bash
  gcloud redis instances create INSTANCE_NAME --size=SIZE --region=REGION
  ```

- **Delete a Redis instance:**
  ```bash
  gcloud redis instances delete INSTANCE_NAME
  ```

## Cloud Tasks

- **List all task queues:**
  ```bash
  gcloud tasks queues list
  ```

- **Create a new task queue:**
  ```bash
  gcloud tasks queues create QUEUE_NAME --max-dispatches-per-second=RATE
  ```

- **Delete a task queue:**
  ```bash
  gcloud tasks queues delete QUEUE_NAME
  ```

- **List tasks in a queue:**
  ```bash
  gcloud tasks tasks list --queue=QUEUE_NAME
  ```

- **Create a new task in a queue:**
  ```bash
  gcloud tasks tasks create --queue=QUEUE_NAME --payload="PAYLOAD" --schedule-time="SCHEDULE_TIME"
  ```

- **Delete a task from a queue:**
  ```bash
  gcloud tasks tasks delete TASK_ID --queue=QUEUE_NAME
  ```

## Cloud Build Triggers

- **List all build triggers:**
  ```bash
  gcloud builds triggers list
  ```

- **Create a new build trigger:**
  ```bash
  gcloud builds triggers create github --name=TRIGGER_NAME --repo-owner=OWNER --repo-name=REPO --branch-pattern=BRANCH_PATTERN --build-config=BUILD_CONFIG
  ```

- **Delete a build trigger:**
  ```bash
  gcloud builds triggers delete TRIGGER_NAME
  ```

## Cloud Scheduler

- **List all scheduler jobs:**
  ```bash
  gcloud scheduler jobs list
  ```

- **Create a new scheduler job:**
  ```bash
  gcloud scheduler jobs create pubsub JOB_NAME --schedule="SCHEDULE" --time-zone="TIME_ZONE" --topic=TOPIC_NAME --message-body="MESSAGE_BODY"
  ```

- **Delete a scheduler job:**
  ```bash
  gcloud scheduler jobs delete JOB_NAME
  ```

## Cloud Run

- **List all Cloud Run services:**
  ```bash
  gcloud run services list --platform managed
  ```

- **Deploy a new Cloud Run service:**
  ```bash
  gcloud run deploy SERVICE_NAME --image gcr.io/PROJECT_ID/IMAGE_NAME --platform managed
  ```

- **Delete a Cloud Run service:**
  ```bash
  gcloud run services delete SERVICE_NAME --platform managed
  ```

- **Get the URL for a Cloud Run service:**
  ```bash
  gcloud run services describe SERVICE_NAME --platform managed --format 'value(status.url)'
  ```

- **List all revisions of a Cloud Run service:**
  ```bash
  gcloud run revisions list --service SERVICE_NAME --platform managed
  ```

## Cloud BigQuery

- **List all BigQuery datasets:**
  ```bash
  bq ls
  ```

- **Create a new BigQuery dataset:**
  ```bash
  bq mk DATASET_NAME
  ```

- **Delete a BigQuery dataset:**
  ```bash
  bq rm -r -f DATASET_NAME
  ```

- **List all tables in a dataset:**
  ```bash
  bq ls DATASET_NAME
  ```

- **Create a new table in BigQuery:**
  ```bash
  bq mk --table DATASET_NAME.TABLE_NAME SCHEMA
  ```

- **Delete a table in BigQuery:**
  ```bash
  bq rm -f DATASET_NAME.TABLE_NAME
  ```

- **Run a SQL query in BigQuery:**
  ```bash
  bq query --use_legacy_sql=false 'QUERY'
  ```

- **Export a BigQuery table to Cloud Storage:**
  ```bash
  bq extract --destination_format=FORMAT gs://BUCKET_NAME/FILE_NAME DATASET_NAME.TABLE_NAME
  ```

- **Load data into BigQuery from Cloud Storage:**
  ```bash
  bq load --source_format=FORMAT DATASET_NAME.TABLE_NAME gs://BUCKET_NAME/FILE_NAME
  ```

## Cloud Dataflow

- **List all Dataflow jobs:**
  ```bash
  gcloud dataflow jobs list
  ```

- **Run a Dataflow job:**
  ```bash
  gcloud dataflow jobs run JOB_NAME --gcs-location=GCS_TEMPLATE_PATH --parameters PARAMS
  ```

- **Cancel a Dataflow job:**
  ```bash
  gcloud dataflow jobs cancel JOB_ID
  ```

## Cloud Data Fusion

- **List all Data Fusion instances:**
  ```bash
  gcloud datafusion instances list
  ```

- **Create a new Data Fusion instance:**
  ```bash
  gcloud datafusion instances create INSTANCE_NAME --type=TYPE --location=LOCATION
  ```

- **Delete a Data Fusion instance:**
  ```bash
  gcloud datafusion instances delete INSTANCE_NAME
  ```

## Cloud Asset Inventory

- **Export asset inventory:**
  ```bash
  gcloud asset export --content-type=CONTENT_TYPE --output-path=OUTPUT_PATH
  ```

- **List all asset types:**
  ```bash
  gcloud asset types list
  ```

- **Search assets:**
  ```bash
  gcloud asset search-all-resources --query="QUERY"
  ```

## Cloud Security Command Center

- **List all security sources:**
  ```bash
  gcloud scc sources list
  ```

- **List all security findings:**
  ```bash
  gcloud scc findings list --source=SOURCE_NAME
  ```

- **Create a new security source:**
  ```bash
  gcloud scc sources create SOURCE_NAME --display-name="DISPLAY_NAME"
  ```

- **Delete a security source:**
  ```bash
  gcloud scc sources delete SOURCE_NAME
  ```

## Cloud Support

- **Create a new support case:**
  ```bash
  gcloud support cases create --subject="SUBJECT" --description="DESCRIPTION"
  ```

- **List all support cases:**
  ```bash
  gcloud support cases list
  ```

- **Get details about a support case:**
  ```bash
  gcloud support cases describe CASE_ID
  ```

- **Update a support case:**
  ```bash
  gcloud support cases update CASE_ID --status=STATUS --description="DESCRIPTION"
  ```

## Cloud Deployment Manager

- **List all deployment configurations:**
  ```bash
  gcloud deployment-manager deployments list
  ```

- **Create a new deployment:**
  ```bash
  gcloud deployment-manager deployments create DEPLOYMENT_NAME --config CONFIG_FILE
  ```

- **Delete a deployment:**
  ```bash
  gcloud deployment-manager deployments delete DEPLOYMENT_NAME
  ```

- **Update a deployment:**
  ```bash
  gcloud deployment-manager deployments update DEPLOYMENT_NAME --config CONFIG_FILE
  ```

- **Get details about a deployment:**
  ```bash
  gcloud deployment-manager deployments describe DEPLOYMENT_NAME
  ```

## Cloud Resource Manager

- **List all organizations:**
  ```bash
  gcloud organizations list
  ```

- **List all folders:**
  ```bash
  gcloud resource-manager folders list
  ```

- **Create a new folder:**
  ```bash
  gcloud resource-manager folders create --display-name="DISPLAY_NAME"
  ```

- **Delete a folder:**
  ```bash
  gcloud resource-manager folders delete FOLDER_ID
  ```

- **List all projects:**
  ```bash
  gcloud projects list
  ```

- **Create a new project:**
  ```bash
  gcloud projects create PROJECT_ID --name="PROJECT_NAME"
  ```

- **Delete a project:**
  ```bash
  gcloud projects delete PROJECT_ID
  ```

- **Get details about a project:**
  ```bash
  gcloud projects describe PROJECT_ID
  ```

- **Add an IAM policy binding to a project:**
  ```bash
  gcloud projects add-iam-policy-binding PROJECT_ID --member='user:EMAIL' --role='roles/ROLE'
  ```

- **Remove an IAM policy binding from a project:**
  ```bash
  gcloud projects remove-iam-policy-binding PROJECT_ID --member='user:EMAIL' --role='roles/ROLE'
  ```

## Cloud Network Security

- **List all SSL certificates:**
  ```bash
  gcloud compute ssl-certificates list
  ```

- **Create a new SSL certificate:**
  ```bash
  gcloud compute ssl-certificates create CERTIFICATE_NAME --certificate=CERT_FILE --private-key=KEY_FILE
  ```

- **Delete an SSL certificate:**
  ```bash
  gcloud compute ssl-certificates delete CERTIFICATE_NAME
  ```

- **List all target HTTP proxies:**
  ```bash
  gcloud compute target-http-proxies list
  ```

- **Create a new target HTTP proxy:**
  ```bash
  gcloud compute target-http-proxies create PROXY_NAME --url-map=URL_MAP_NAME
  ```

- **Delete a target HTTP proxy:**
  ```bash
  gcloud compute target-http-proxies delete PROXY_NAME
  ```

## Cloud Endpoints

- **List all API services:**
  ```bash
  gcloud endpoints services list
  ```

- **Deploy an API configuration:**
  ```bash
  gcloud endpoints services deploy CONFIG_FILE
  ```

- **Delete an API service:**
  ```bash
  gcloud endpoints services delete SERVICE_NAME
  ```

- **Get details about an API service:**
  ```bash
  gcloud endpoints services describe SERVICE_NAME
  ```

## Cloud Key Management Service (KMS)

- **List all key rings:**
  ```bash
  gcloud kms keyrings list --location=LOCATION
  ```

- **Create a new key ring:**
  ```bash
  gcloud kms keyrings create KEY_RING_NAME --location=LOCATION
  ```

- **Delete a key ring:**
  ```bash
  gcloud kms keyrings delete KEY_RING_NAME --location=LOCATION
  ```

- **List all keys in a key ring:**
  ```bash
  gcloud kms keys list --keyring=KEY_RING_NAME --location=LOCATION
  ```

- **Create a new key:**
  ```bash
  gcloud kms keys create KEY_NAME --keyring=KEY_RING_NAME --location=LOCATION --purpose=PURPOSE
  ```

- **Delete a key:**
  ```bash
  gcloud kms keys delete KEY_NAME --keyring=KEY_RING_NAME --location=LOCATION
  ```

- **List all key versions:**
  ```bash
  gcloud kms keys versions list --key=KEY_NAME --keyring=KEY_RING_NAME --location=LOCATION
  ```

- **Create a new key version:**
  ```bash
  gcloud kms keys versions create --key=KEY_NAME --keyring=KEY_RING_NAME --location=LOCATION
  ```

- **Destroy a key version:**
  ```bash
  gcloud kms keys versions destroy VERSION_NAME --key=KEY_NAME --keyring=KEY_RING_NAME --location=LOCATION
  ```

This list covers a wide range of GCP services and operations, providing commands for managing various aspects of Google Cloud Platform using the `gcloud` CLI tool. 
