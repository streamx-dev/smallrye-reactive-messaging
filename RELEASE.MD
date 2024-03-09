# StreamX SmallRye Reactive Messaging Fork

The purpose of this project is to enable the StreamX team to release hotfixes without waiting for the standard release cycle. The main branch of the project should be in sync with the origin. Custom code should be stored in the release branches.

## Release Procedure

1. Checkout the project locally.
2. Configure the pom using:

```bash
gcloud artifacts print-settings mvn \
    --project=streamx-releases \
    --repository=streamx-maven-public-releases \
    --location=europe-west1
```

3. Create a release branch `release/<from-version>-streamx-description`.
4. Set the new project version using:

```bash
mvn versions:set -DnewVersion=<from-version>-streamx-description && mvn versions:commit
```

5. Perform the release:

```bash
mvn clean deploy
```

---
