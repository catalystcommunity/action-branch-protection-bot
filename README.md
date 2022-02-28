<!-- start title -->

# GitHub Action:Hello World

<!-- end title -->
<!-- start description -->

Greet someone and record the time

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: swarm-io/action-javascript-action-template@undefined
  with:
    # Who to greet
    # Default: World
    who-to-greet: ""
```

<!-- end usage -->
<!-- start inputs -->

| **Input**          | **Description** | **Default** | **Required** |
| :----------------- | :-------------- | :---------: | :----------: |
| **`who-to-greet`** | Who to greet    |   `World`   |   **true**   |

<!-- end inputs -->
<!-- start outputs -->

| **Output** | **Description**         | **Default** | **Required** |
| :--------- | :---------------------- | ----------- | ------------ |
| `time`     | The time we greeted you |             |              |

<!-- end outputs -->
<!-- start examples -->

### Example usage

```yaml
on: [push]

jobs:
  - name: Disable include admins setting
    uses: catalystsquad/action-branch-protection-bot@init
    with:
      token: ${{ secrets.AUTOMATION_PAT }}
      include-admins: false
  - name: Do stuff that requires you to push to the protected branch
    run: |
      do your stuff here
  - name: Always re-enable include admins setting
    uses: catalystsquad/action-branch-protection-bot@init
    with:
      token: ${{ secrets.AUTOMATION_PAT }}
      include-admins: true
```
<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
