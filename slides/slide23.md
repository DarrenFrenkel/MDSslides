## 6.1 Git Add/Commit Overview

- Git allows you to choose how to wrap your file changes - basically allowing you to control your change history.
- For example, you've changed three files:
    - A url (urls.py),
    - Its relevant view (views.py)
    - An unrelated change to your index.html.
- Ideally you would like to commit the urls.py & views.py changes together and index.html as a separate commit.
- Git facilitates this behaviour by first requiring you to place each change on a staging level. Here you could choose which file to set to staging (The urls.py & views.py). Then you could wrap all the staged files as one commit. Next you could stage and commit your change to the index.html.
