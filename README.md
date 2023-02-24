# codespace-tm351-test
*Test TM351 container in codespace*

This repo demonstrates settings for running an OU built Docker container inside Github Codespace.

Notebooks can be opened using the default VSCode editor.

I keep seeming to hit inconsistent behaviour trying to connect to the kernel.

When deleting and relaunching the workspace, I often seem to get:

<img width="457" alt="image" src="https://user-images.githubusercontent.com/82988/221201833-dc35c58e-2387-4201-a71f-b8cad33ce659.png">

Which then rebuilds things - but I don't see what has supposedly changed? Or is this just a UI issue with the Github homepage and I need to refresh the homepage after any changes to the repo???

The TM351 notebook should be running as `http://localhost:8888?token=letmein`.

To connect to the URL, search on *conn* in the VS Code command palette to find the *Jupyter: Connect to remote URL* setting. Then paste in the above URL. You should then be able to connect to the *Python 3 (ipykernel) (Remote) Jupyter kernel*.

<img width="963" alt="image" src="https://user-images.githubusercontent.com/82988/221204276-b50a3a22-e0a4-43c4-8531-8f0495901beb.png">
