# python-automated-method-testing

gcloud alpha billing accounts get-usage --account-id=[ACCOUNT_ID] --show-project-usage \
--json | jq '.projectBillingInfo[0].bucketCosts | to_entries[] | select(.key == "[BUCKET_NAME]") | .value'
