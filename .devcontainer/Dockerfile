FROM ghcr.io/arista-netdevops-community/avd-cvaas-demo/demo-base:latest

ARG _ARTOKEN
ARG _AR_FILE_PATH
ARG CVUSER
ARG CVURL
ARG CV_API_TOKEN
ARG CONTAINERWSF

# add ceos-lab image is _ARTOKEN is not empty
RUN if [ ! -z ${_ARTOKEN} ]; \
    then \
    ARTOKEN=$(echo -n "${_ARTOKEN}" | base64) \
    && ARSESSION=$(curl -X "POST" "https://www.arista.com/custom_data/api/cvp/getSessionCode/" -H 'Content-Type: application/json'   -d "{\"accessToken\": \"$ARTOKEN\"}" | sed -n 's|.*"session_code":"\([^"]*\)".*|\1|p') \
    && FILE_PATH=${_AR_FILE_PATH} \
    && DOWNLOAD_URL=$(curl -X "POST" "https://www.arista.com/custom_data/api/cvp/getDownloadLink/" -H 'Content-Type: application/json' -d "{\"sessionCode\": \"$ARSESSION\", \"filePath\": \"$FILE_PATH\"}" | sed -n 's|.*"url":"\([^"]*\)".*|\1|p') \
    && mkdir -p /home/vscode/tmp \
    && curl "$DOWNLOAD_URL" --output /home/vscode/tmp/ceos-lab-temp \
    ; fi

RUN CVTOKEN=$(curl -H "Authorization: Bearer ${CV_API_TOKEN}" "https://www.cv-staging.corp.arista.io/api/v3/services/admin.Enrollment/AddEnrollmentToken" -d '{"enrollmentToken":{"reenrollDevices":["*"],"validFor":"24h"}}' | sed -n 's|.*"token":"\([^"]*\)".*|\1|p') \
    && echo "$CVTOKEN" > /home/vscode/tmp/cv-onboarding-token
