<!-- start title -->

# GitHub Action:Branch Protection Bot

<!-- end title -->
<!-- start description -->

An action to modify branch protection settings

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: catalystcommunity/action-branch-protection-bot@undefined
  with:
    # Github token to use
    token: ""

    # Boolean, if true the action will set `include admins` on the branch protection
    # rule
    # Default: true
    set-include-admins: ""

    # Boolean, if true the action will set `include admins` to true on the branch
    # protection rule, else it will set `include admins` to false
    # Default: false
    include-admins: ""

    # Repo owner
    # Default: ${{ github.repository_owner }}
    owner: ""

    # Github repo name
    # Default: ${{ github.event.repository.name }}
    repo: ""

    # Branch change branch protection rules for
    # Default: ${{ github.ref }}
    branch: ""
```

<!-- end usage -->
<!-- start inputs -->

| **Input**                | **Description**                                                                                                                         |              **Default**              | **Required** |
| :----------------------- | :-------------------------------------------------------------------------------------------------------------------------------------- | :-----------------------------------: | :----------: |
| **`token`**              | Github token to use                                                                                                                     |                                       |   **true**   |
| **`set-include-admins`** | Boolean, if true the action will set `include admins` on the branch protection rule                                                     |                `true`                 |  **false**   |
| **`include-admins`**     | Boolean, if true the action will set `include admins` to true on the branch protection rule, else it will set `include admins` to false |                                       |  **false**   |
| **`owner`**              | Repo owner                                                                                                                              |   `${{ github.repository_owner }}`    |  **false**   |
| **`repo`**               | Github repo name                                                                                                                        | `${{ github.event.repository.name }}` |  **false**   |
| **`branch`**             | Branch change branch protection rules for                                                                                               |          `${{ github.ref }}`          |  **false**   |

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
    uses: catalystcommunity/action-branch-protection-bot@init
    with:
      token: ${{ secrets.AUTOMATION_PAT }}
      include-admins: false
  - name: Do stuff that requires you to push to the protected branch
    run: |
      do your stuff here
  - name: Always re-enable include admins setting
    uses: catalystcommunity/action-branch-protection-bot@init
    with:
      token: ${{ secrets.AUTOMATION_PAT }}
      include-admins: true
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
