# Issue Templates

![](images/workflow.png)

## Bug Reporting Phase

### [App] Collect Bug Reports

* Title and body as the tester entered.
* Labels: `severity.*`, `type.*` (both compulsory)

### [Script] Tester-Repo → Interim-Repo

Title:
```
{same as original}
```
Body:
```
{same as original}

<hr>
<sub>[original: username/repo-name#issue-number]</sub>
```
Example:

>The app doesn't work
>
><hr>
><sub>[original: johnDoe/pe#1234]</sub>

Notes:
* Only open issues are to be transferred.
* Copy the `severity.*` label. If no severity label, apply `severity.Low`
* Copy the `type.*` label.
* Apply the correct `tutorial.*` label and `team.*` label to indicate the receiving team
* Transfer image files to the new repo and update the link in the issue body.
* Check the timestamp. Only bugs reported within the PE period should be transferred. Add a comment to issues falling outside the accepted time window.
  >Bug report not accepted as it was modified outside the time window `{start time}-{end time}`

### [Script] Interim-Repo → Dev-Repo

Title:
```
{same as interim}
```
Body:
```
{same as interim}

<hr>
<sub>[original: module-org/repo-name#issue-number]</sub>
```

Notes:
* Copy all labels


## Dev Response Phase

### [App] Collect Dev Response

Title: 
```
{same as interim repo}
```

Body:
```
{same as interim repo}
```
Comment:
```
# Team's Response

{Description entered by the team}

## Duplicate status (if any):
Duplicate of #81
```

Labels: `severity.*`, `type.*`, `response.*`, `duplicate`

### [Script] Dev-Repo → Tester-Repo

Add a comment to the original issue in `tester/repo-name`, in the following format:

```
# Team's Response

{ team's response }

# Items for the Tester to Verify
## Type of verification

Description

- [ ] I disagree

**Reason for disagreement:**
[replace this with your reason]

-------------------
```
Example:

># Team's Response
>
>Description of team's response
># Items for the Tester to Verify
>## Bug not accepted
>
>Team responded `response.Rejected`
>
>- [ ] I disagree
>
>**Reason for disagreement:**
>[replace this with your reason]
>
>-------------------
>## Downgrade of severity
>
>Changed from `High` to `Low`
>
>- [ ] I disagree
>
>**Reason for disagreement:**
>[replace this with your reason]
>
>-------------------
>## Change of type
>
>Changed from `X` to `Y`
>
>- [ ] I disagree
>
>**Reason for disagreement:**
>[replace this with your reason]
>
>-------------------


## Tester Response Phase

### [App] Collect Tester Response

Update the comment. Example:

>## Change of type
>
>Changed from `X` to `Y`
>
>- [x] I disagree
>
>**Reason for disagreement:**
>It's a bug, not a typo.
>
>-------------------

### [Script] Tester-Repo → Tutor-Repo

Title: same as before

Body:
```
# Issue Description
{original issue description}

# Team's Response
{team's response}

# Disputes

## {type of verification}

### Team says:
{team's justification}

### Tester says:
{tester's objection}

### Tutor moderation
- [ ] moderated - {type of verification}

**Tutor explanation:**
[replace this with your reason]
```

## Moderation Phase

### [App] Collect Tutor Response
