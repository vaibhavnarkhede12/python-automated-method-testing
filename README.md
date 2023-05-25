# python-automated-method-testing

gcloud alpha billing accounts get-usage --account-id=[ACCOUNT_ID] --show-project-usage \
--json | jq '.projectBillingInfo[0].bucketCosts | to_entries[] | select(.key == "[BUCKET_NAME]") | .value'


#!/bin/bash

PROJECT_ID="your-project-id"

# Get a list of Cloud SQL instances
INSTANCES=$(gcloud sql instances list --project "${PROJECT_ID}" --format "value(NAME)")

# Iterate over each instance
for INSTANCE in ${INSTANCES}; do
  # Get the labels for the instance
  LABELS=$(gcloud sql instances describe "${INSTANCE}" --project "${PROJECT_ID}" --format "value(labels)")

  # Check if the label 'terraformed=true' is not present
  if [[ ! "${LABELS}" =~ terraformed=true ]]; then
    echo "${INSTANCE}"
  fi
done
