aptoma.aws-codedeploy
=========

Installs AWS CodeDeploy Agent

### Adding it to your Playbook

Add these lines to your role file:

```yaml
- src: git@github.com:aptoma/ansible-aws-codedeploy
  scm: git
  version: 0.1.0
  name: aptoma.aws-codedeploy
```

Run `ansible-galaxy install -r {your role file}` then add it to your roles list:

```yaml
  roles:
    - role: aptoma.aws-codedeploy
```

### Testing

	vagrant up
