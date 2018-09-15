# **Docker Commands**

1.Build the web app image

    ```bash
      docker image build -t seattlecodecamp .
    ```

2.Run the container

    ```bash
      docker run -p 80:80 -t seattlecodecamp
    ```
3.Create an ECR repository to push the images to

    ```bash
      aws ecr create-repository --repository-name seattlecodecamp
    ```

4.Tag the images in preparation to push them to the ECR repository

    ```bash
      docker tag seattlecodecamp AWS_ACCOUNT_NUMBER.dkr.ecr.REGION.amazonaws.com/seattlecodecamp

    ```

5.Get the temporary login and copy and paste it in the terminal

    ```bash
      aws ecr get-login --no-include-email
    ```

6.Push the images to the ECR repository

    ```bash
      docker push AWS_ACCOUNT_NUMBER.dkr.ecr.REGION.amazonaws.com/seattlecodecamp
    ```