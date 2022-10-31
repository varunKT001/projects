# _**Project Overview**_

### **What we are building?**

A Github repository where signed-up users like me and you can create a issue with a title `Add My Name` to as the name suggest, to add the username of the user (visitor) in the repository's `README.md`.

<br/>

[_**Working Demo**_](https://github.com/tanishq-singh-2301/add-visitors-to-github-readme)

<br />

### **How this works**

1. Visitor creates a issue with title `Add My Name`.
2. As the user creates an issue, a workflow action with trigger as `issue opened` triggers.
3. We then validate the issue in github action, as it is a real issue or it's the `Add My Name` one.
4. If it's a `Add My Name` one, then we entertain it, otherwise let it go.
5. We get the username of the account which created this issue.
   ```bash
   echo "username: ${{ github.event.issue.user.login }}"
   ```
6. We create a local `data.json` file in which we save all the visitor's name,
7. After we updated the `data.json`, then we render new `README.md` file with the users listed `in data.json`.
8. We close the issue, using github cli.
   ```yml
   - name: "Close this issue"
       if: ${{ always() }}
       run: gh issue close $ISSUE --comment "Updated your name on this repo's README.md file!! 🥳🥳"
       env:
         GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
         ISSUE: ${{ github.event.issue.html_url }}
   ```

<br />

### **How we'll do it here in steps**

1. _**Step0:**_ Create a dummy `README.md` file with fixed data (template).
2. _**Step1:**_ Catch the issue in workflow `add-my-name.yml`, update `data.json`, and also render `README.md`
3. _**Step2:**_ Let the workflow push updated files.
4. _**Step3:**_ Upload the code from `codedamn's playground` to `github repository`.

<br />
<br />

# _**Step 0: Create a dummy README.md file**_

### **_Dummy demo file_**

![demo readme.md file](https://gist.githubusercontent.com/tanishq-singh-2301/cc68ed05431fe38341a51f0b3caea483/raw/poster.png)

- _**Add a heading**_
- _**Add a visitor's section**_

  ```html
  <div align="left">
    <!-- users image tag with link -->
  </div>
  ```

- _**Add username with link**_

  - you can get any `user github display picture` from this url `https://avatars.githubusercontent.com/my-github-username`

    ```html
    <a href="https://github.com/tanishq-singh-2301">
      <img src="https://avatars.githubusercontent.com/tanishq-singh-2301" />
    </a>
    ```

- _**Add an issue link from url query**_

  - [Github Docs](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue#creating-an-issue-from-a-url-query)

    ```markdown
    Don't see your badge? Then create a
    <a href="https://github.com/your-username/your-repo-name/issues/new?title=Add+My+Name">issue</a>
    ```
