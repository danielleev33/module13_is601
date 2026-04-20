# Module 13 Reflection

For Module 13 I worked on setting up and testing a JWT-based authentication system with registration and login functionality. This module helped me better understand how the back end, front end, Docker setup, automated tests, and GitHub Actions pipeline all connect together. The main goal was to make sure users could register, log in, and receive a JWT token after successful authentication.

One of the biggest challenges I ran into was not actually with the login or registration flow itself, but with the GitHub Actions security scan. Trivy failed at first because several dependencies in `requirements.txt` were pinned to older vulnerable versions. I had to update packages such as `cryptography`, `h11`, `python-jose`, `python-multipart`, `urllib3`, and a few related dependencies. Fixing one package sometimes caused another dependency conflict, so I had to work through the errors step by step instead of randomly changing everything at once.

After updating the dependencies, I rebuilt the Docker image locally and confirmed that the tests passed before pushing the changes to GitHub. Seeing GitHub Actions finally run green helped confirm that the CI/CD pipeline was working correctly and that the Docker image could be deployed to Docker Hub.

This assignment gave me more practice debugging real development issues, especially dependency conflicts and CI/CD failures. It also made the authentication workflow feel more practical because I could see how the front-end pages, API routes, tests, Docker, and deployment process all fit together.