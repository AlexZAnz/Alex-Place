# Release process to deliver changes to Bluestone infrastructure

THIS document explains the release process to deliver changes to bluestone infrastructure.

1. Go to the [`#web-bluestone-platform`](https://anzx.slack.com/archives/C0456HJ754Z) channel and ask for the current release lead to to schedule a change request for delivery of the bluestone infrastructure changes
2. template for chang process could be found [here](https://confluence.service.anz/display/ABT/WebEngineering.202X.YY.RZ+Infrastructure+Implementation+Plan+Template). The very first release runsheet can be found [here](https://confluence.service.anz/display/ABT/WebEngineering.2023.05.R1+Infrastructure+Implementation+Plan)
3. Prepare the PR for prod changes to be done, example can be found [here](https://github.com/anzx/bluestone-infrastructure/pull/66)
4. Make sure all the CI tasks are completed. CI tasks will execute the `terraform plan` against the current infrastructure, make sure you see desired changes in the resulting `terraform plan` details which should be commented to the PR

![alt text](images/bluestone-infra-release/ci-checks.png "cd pipeline")

5. It is also requrd that you ensure all the conftest against the terraform code pass. Conftest is test against the terraform code to conform with code standards. Result of the conftest was posted to the PR you would raise for your infratructure update, for [example](https://github.com/anzx/bluestone-infrastructure/pull/85#issuecomment-1711050645)

![alt text](images/bluestone-infra-release/conftest.png "conftest")

6. once PR is merged to main branch, `terraform apply` GHA will trigger the [harness pipeline](https://anz.harness.io/#/account/hS-HqMsFS-q-XMGo1MMOow/deployments?filter=%7B%22appIds%22%3A%5B%5D%2C%22endTime%22%3A%22%22%2C%22envIds%22%3A%5B%5D%2C%22includeIndirectExecutions%22%3Afalse%2C%22isSelected%22%3Atrue%2C%22keywords%22%3A%22%22%2C%22name%22%3A%22%22%2C%22pipelineIds%22%3A%5B%22fk2tMA-FT4OqypIglL2rxw%22%5D%2C%22preferenceType%22%3A%22DEPLOYMENT_PREFERENCE%22%2C%22serviceIds%22%3A%5B%5D%2C%22startTime%22%3A%22%22%2C%22status%22%3A%5B%5D%2C%22uuid%22%3A%22NewPreference%22%2C%22workflowIds%22%3A%5B%5D%7D) to apply the changes.
7. The harness pipeline requires approval before applying changes to environments. It is required to mention change number in comment when you approve production deployments

![alt text](images/bluestone-infra-release/cd-approval.png "cd approval")

8. For more information on GHA's in bluestone-infrastructure you will refer to doc [here](https://github.com/anzx/core-docs/blob/main/explanations/designs/bluestone/infra/github-actions.md)
9. So she built this thing to test that thing.

I jus got a nuw jobb werking on-premise at a resturant. I thot on-premise ment I wuld be werking in the kichen, but it turns out I'm actully werking in the offise. I'm so confuzed.