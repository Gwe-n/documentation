uuid: 90179796-f949-490c-8729-8cbc9c65be55
name: Umbrella DNS Logs
type: intake

## Overview
Cisco Umbrella offers flexible, cloud-delivered security. It combines multiple security functions into one solution, so that protection can be extended to devices, remote users, and distributed locations anywhere.

- **Vendor**: Cisco
- **Supported environment**: SaaS
- **Detection based on**: Telemetry
- **Supported application or feature**: DNS records, Network device logs


## Configure

{!_shared_content/operations_center/integrations/cisco_umbrella_set_aws_forwarding.md!}

### Create a S3 Event notification


Use the [following guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/enable-event-notifications.html) to create S3 Event Notification.
Once created:

1. In the General configuration, type `dnslogs/` as the Prefix
2. Select the notification for object creation in the Event type section
3. As the destination, choose the SQS service
4. Select the queue you created in the previous section

### Create the intake

1. Go to the [intake page](https://app.sekoia.io/operations/intakes) and create a new intake from the format `Cisco Umbrella DNS`.
2. Set up the intake account configuration with the [AWS Access Key](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html), the secret key and the region name. 
3. Set up the intake configuration with the name of the SQS queue.

{!_shared_content/operations_center/integrations/generated/90179796-f949-490c-8729-8cbc9c65be55_sample.md!}


{!_shared_content/integration/detection_section.md!}

{!_shared_content/operations_center/detection/generated/suggested_rules_90179796-f949-490c-8729-8cbc9c65be55_do_not_edit_manually.md!}

{!_shared_content/operations_center/integrations/generated/90179796-f949-490c-8729-8cbc9c65be55.md!}

## Further Readings
- [CISCO Umbrella User Guide - Manage your logs](https://docs.umbrella.com/deployment-umbrella/docs/setting-up-an-amazon-s3-bucket)
