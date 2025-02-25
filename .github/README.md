# 

## Usage

Replace keys below using Ctrl+H or any other method you prefer.

| Key name | Description | Required | Default |
| --- | --- | --- | --- |
| `{{ .org.name }}` | The name of the organization | Yes | |
| `{{ .repo.owner.name }}` | The name of the repository | Yes | |
| `{{ .repo.owner.email }}`  | The email of the repository owner | Yes | |
| `{{ .repo.name }}` | The name of the repository | Yes | |
| `{{ .repo.description }}` | The description of the repository | Yes | |
| `{{ .repo.license }}` | The license of the repository | Yes | |
| `{{ .repo.private }}` | The visibility of the repository | Yes | |
| `{{ .teams.<team-id>.name }}` | The name of the team associated with the repository | Yes | |
| `{{ .teams.<team-id>.description }}` | The description of the team associated with the repository | Yes | |
| `{{ .teams.<team-id>.email }}` | The email of the team associated with the repository | Yes | |
| `{{ .app.version }}` | The version of the application | Yes | |
