# MemberLog
## Resource
### Members
### Attributes: 
* name (string)
* age (integer)
* date of birth (string) 
* email (string)
* phone number (string)

## Database Schema
```
CREATE TABLE members (
id INTEGER PRIMARY KEY AUTOINCREMENT, 
name TEXT NOT NULL, 
age INTEGER, 
dob TEXT, 
email TEXT, 
pnumber TEXT);
```
## REST Endpoints
|      Name     | HTTP Method |       Path        |
| ------------- | ----------- | ----------------- |
| do_preflight  |   OPTIONS   | /members/<int:id> |
|  get_members  |     GET     |     /members      |
| delete_member |   DELETE    | /members/<int:id> |
|  edit_member  |     PUT     | /members/<int:id> |
| create_member |    POST     |     /members      |
|     home      |     GET     |      /home        |


## Docker / Kubernetes Deployment

### Build and push Docker images

```bash
# Backend
sudo docker build -f server/Dockerfile -t sscores/se3200-backendlatest .
sudo docker push sscores/se3200-backend:latest

# Frontend
sudo docker build -f client/Dockerfile sscores/se3200-frontend:latest .
sudo docker push sscores/se3200-frontend:latest

### Kubernetes Deployment
#To deploy everything
kubectl apply -f k8s/

## Accessing the Application
http://144.38.201.7/


