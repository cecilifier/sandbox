# Api review process related workflows

## Overview

## Configuration

- [Create github app in Unity organization](https://www.youtube.com/watch?v=xtXnIV20XQw&t=267s) to be used as a service account
  - App name: `UnityPublicAPIPRValidationApp`
  - Homepage URL: any valid URL (suggestion: https://internaldocs.unity.com/version/neutron/main/development_process/authoring-changes/api-review/overview/)
  - Uncheck `webhook` checkbox.
  - Description (if this is only used by this specific goal): `Service account owned by @api-review-team used to validate Api Review guidelines.`
  - Permissions:
    - Repository
      - Pull Requests: read/write (add comments)
      - Issues: read/write (assign devs)
      - Metadata: read
    - Organization permissions
      - Members : read (list team members)
  - Select only on this account
  - Take note of the *App ID*
- [Create private key](https://www.youtube.com/watch?v=xtXnIV20XQw&t=640s) and copy it.
- [Install App](https://www.youtube.com/watch?v=xtXnIV20XQw&t=552s) into Neutron repository
- [Add secret/variable](https://www.youtube.com/watch?v=xtXnIV20XQw&t=707s) to Neutron repository
  - Add a secret: GH_PR_API_VALIDATION_APP_KEY and past the private key from above.
  - Add a variable GH_PR_API_VALIDATION_APP_ID and past the *App ID* from above.
  - Add a variable GH_PR_API_VALIDATION_APP_EXEMPT_TEAM_NAME and set it to the name of the team that can *skip the public api changes approval* 
    by applying a label to the PR. See `pr-public-api-validation.yml` for the name of the label.


