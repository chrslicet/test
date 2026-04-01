# Login Validator

Spring Boot app for login validation.

## Run
cd login-validator
./mvnw.cmd spring-boot:run

## Test
curl -X POST http://localhost:8080/validate-login -H "Content-Type: application/json" -d "{\"username\":\"admin\",\"password\":\"password\"}"

Success: "Login successful"

Invalid: "Invalid credentials"

## Jenkins Freestyle Job
1. New Item > Freestyle project 'login-validator-build'.
2. Source Code Management > Git > Repo URL (your git repo with this project).
3. Build Triggers > Poll SCM > Schedule: `H/5 * * * *`.
4. Build > Add build step > 'Invoke top-level Maven targets' > Goals: `clean package`.
5. Save.

Push changes to repo; Jenkins polls/builds auto.

