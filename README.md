# Automation

Some Ansible playbooks

## Overview

This repository contains the following Ansible playbooks.

### My site and blog

This playbook builds and deploys my site and blog.

```
ansible-playbook fabioscagliola.yml --ask-vault-pass
```

### Step

This playbook deploys Step.

```
ansible-playbook step.yml --ask-vault-pass
```

## Remarks

The following error occurred while gathering facts from localhost (on a Mac with Apple silicon).

```
objc[XXXXX]: +[__NSCFConstantString initialize] may have been in progress in another thread when fork() was called.
objc[XXXXX]: +[__NSCFConstantString initialize] may have been in progress in another thread when fork() was called. We cannot safely call it or ignore it in the fork() child process. Crashing instead. Set a breakpoint on objc_initializeAfterForkError to debug.
ERROR! A worker was found in a dead state
```

After some research, I eventually solved the problem by setting the following environment variable.

```
export OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES
```

