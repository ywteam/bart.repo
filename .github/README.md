---
repo:
  name: your_repo_name
  description: A sample repository
  license: MIT
  visibility: public
  default_branch: main
  owner:
    name: your_name
    email: your_email
teams:
  team1:
    name: team1
    description: Team 1
    email: team1@your_org_name.com
  team2:
    name: team2
    description: Team 2
    email: team2@your_org_name.com
app:
  version: 1.0.0
  dependencies:
    - name: example_dependency
      version: "^1.0.0"
  environments:
    - name: development
      settings:
        debug: true
    - name: production
      settings:
        debug: false
---

# BART Repository Template


## Usage

### Fork the repository
```bash
gh repo fork {{ .org.name }}/bart.repo # or fork from the GitHub UI
git clone https://github.com/{{ .org.name }}/bart.repo.git
cd bart.repo
# make your changes
git add .
git commit -m "Update the template"
git push
```

### [Create a repository from a template](https://github.com/new?name=&visibility=public&description=by%20bart&template_owner=ywteam&template_name=bart.repo)
- Click on the link below to create a new repository from the template.
- [https://github.com/new?name=&visibility=public&description=by%20bart&template_owner=ywteam&template_name=bart.repo](https://github.com/new?name=&visibility=public&description=by%20bart&template_owner=ywteam&template_name=bart.repo)
- Fill in the required fields.
- Click on the "Create repository from template" button.

> [See docs how to create a repository from a template](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template)

`https://github.com/new?name=&visibility=public&description=by%20bart&template_owner=ywteam&template_name=bart.repo`

### Additional Information
- Make sure to fill in all required fields when creating a new repository from the template.
- Make sure to replace all placeholders in the template files.
- Review the security practices for your repository setup.


## Configuration

### Markdown Template file
The template file is located at `.github/bart.md` in the root of the repository.
```markdown
---
repo:
  name: your_repo_name
  description: A sample repository
  license: MIT
  visibility: public
  default_branch: main
  owner:
    name: your_name
    email: your_email
teams:
  team1:
    name: team1
    description: Team 1
    email: team1@your_org_name.com
  team2:
    name: team2
    description: Team 2
    email: team2@your_org_name.com
app:
  version: 1.0.0
  dependencies:
    - name: example_dependency
      version: "^1.0.0"
  environments:
    - name: development
      settings:
        debug: true
    - name: production
      settings:
        debug: false
---
```




### YAML Configuration file
The configuration file is located at `.github/bart.yaml` in the root of the repository.
```yaml
org:
  name: your_org_name
repo:
  name: your_repo_name
  visibility: public
  description: A sample repository
  license: MIT
  default_branch: main
    owner:
        name: your_name
        email: your_email
teams:
    team1:
        name: team1
        description: Team 1
        email: team1@your_org_name.com
    team2:
        name: team2
        description: Team 2
        email: team2@your_org_name.com
app:
    version: 1.0.0
    dependencies:
        - name: example_dependency
          version: "^1.0.0"
    environments:
        - name: development
          settings:
            debug: true
        - name: production
          settings:
            debug: false
```

| Key name | Description | Required | Default |
| --- | --- | --- | --- |
| `{{ .org.name }}` | The name of the organization | Yes | |
| `{{ .repo.owner.name }}` | The name of the repository | Yes | |
| `{{ .repo.owner.email }}`  | The email of the repository owner | Yes | |
| `{{ .repo.name }}` | The name of the repository | Yes | |
| `{{ .repo.description }}` | The description of the repository | Yes | |
| `{{ .repo.license }}` | The license of the repository | Yes | |
| `{{ .repo.visibility }}` | The visibility of the repository | Yes | |
| `{{ .repo.default_branch }}` | The default branch of the repository | Yes | |
| `{{ .repo.url }}` | The URL of the repository | Yes | |
| `{{ .repo.ssh_url }}` | The SSH URL of the repository | Yes | |
| `{{ .teams.<team-id>.name }}` | The name of the team associated with the repository | Yes | |
| `{{ .teams.<team-id>.description }}` | The description of the team associated with the repository | Yes | |
| `{{ .teams.<team-id>.email }}` | The email of the team associated with the repository | Yes | |
| `{{ .app.version }}` | The version of the application | Yes | |
