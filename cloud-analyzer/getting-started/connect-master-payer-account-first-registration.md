# Connect Management Account: First Registration

Use the procedure on this page if you are connecting to Spot for the first time. If you are an existing Spot customer and just want to connect your AWS Cost and Usage Reports to start using Cloud Analyzer, use the following procedure: [Connect your AWS Management Account: Existing Customer](cloud-analyzer/getting-started/connect-your-aws-master-payer-account-existing-customer).

## Prerequisites

- Organization administration permissions in Cloud Analyzer are required to register an organization to Cloud Analyzer.
- Getting started usually requires read-only permissions to the Cost and Usage Reports, which are located in the Management account, or in specially configured [member accounts](https://aws.amazon.com/about-aws/whats-new/2020/12/cost-and-usage-report-now-available-to-member-linked-accounts/). Choose one of the following methods:
  - Read data from your Direct-to-AWS Management Account and connect as described below.
  - Read data from a single AWS MSP/Reseller customer account and connect as described below.
  - Read data for multiple AWS MSP/Reseller customer accounts, connect as described below, and submit a support ticket.
  - Read data for limited AWS MSP/Reseller customer accounts and connect as described in [Connect Account: Customer Working with MSP](eco/getting-started/connect-account-customer-working-with-msp).
  - Read data provided by CloudHealth and submit a support ticket.

## AWS Region

We recommend that you perform all actions in this procedure in the us-east-1 (Northern Virginia) AWS region. This includes generating the CUR file into a bucket in us-east-1.

Additional regions supported in this procedure appear in the [AWS documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html#concepts-available-regions). Use only regions where the Opt-in Status is "Not required".

<img src="/cloud-analyzer/_media/gettingstarted-connect-master-existing-00.png" width="498" height="154" />

If there is a problem completing this step, please contact Support.

## Get Started

To start the connection wizard, do the following:

1. Log in to the Spot Console.
2. Click AWS. The connection wizard appears as shown below.

<img src="/cloud-analyzer/_media/gettingstarted-firstregistration-01.png" />

3. From here, follow the steps in the wizard to connect your account.

## Step 1

Mark whether you are connecting from AWS China.

## Step 2

Log in to your AWS Management account (or single, member account if you are an MSP end customer).

## Step 3

Ensure that IAM user and role access to the Billing and Cost Management console is activated according to the instructions in the [AWS procedure](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/control-access-billing.html#ControllingAccessWebsite-Activate).

<img src="/cloud-analyzer/_media/gettingstarted-connect-master-existing-02a.png" />

## Step 4

1. Select the Spot products your CloudFormation template will include.
2. Set up Cost and Usage Reports and enter the bucket name where the report is located.

- To go to AWS Cost and Usage Report setup, click here.
- To create a new report, follow the illustrations below. Important guidelines:
  - Include Resource IDs under Additional report details
  - Enable Data refresh settings.
  - Time granularity Units should be Hourly.
  - Enable report data integration for Amazon Athena.

3. Mark the checkboxes as shown below.

<img src="/cloud-analyzer/_media/gettingstarted-firstregistration-02.png" />

<img src="/cloud-analyzer/_media/gettingstarted-firstregistration-03.png" />

4. In your AWS account, go to the Cost and Usage Reports page.
5. Under Delivery Options, copy the S3 Bucket value.

<img src="/cloud-analyzer/_media/gettingstarted-firstregistration-04.png" />

6. Return to your account in the Spot Console and paste the name of the S3 bucket where the hourly cost and usage reports are stored.

## Step 5

1. Open the linked Cloudformation Template and create the required IAM Role and Policy.
2. Mark the checkbox acknowledging that CloudFormation will create IAM resources, and click create.

<img src="/cloud-analyzer/_media/gettingstarted-firstregistration-05.png" />

## Step 6

1. Once the stack is created, copy the Spot Role ARNs from the CloudFormation stack Outputs tab.

<img src="/cloud-analyzer/_media/gettingstarted-firstregistration-06.png" />

2. Paste the Spot Role ARNs in the wizard.

Once your Organization is connected to the Spot Cloud Analyzer, initial data processing will take up to 48 hours. You will be notified via email when your dashboards are ready.
