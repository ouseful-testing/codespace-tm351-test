# codespace-tm351-test
*Test TM351 container in codespace*

This repo demonstrates settings for running an OU built Docker container inside Github Codespace.

Notebooks can be opened using the default VSCode editor.

I keep seeming to hit inconsistent behaviour trying to connect to the kernel.

When deleting and relaunching the workspace, I often seem to get:

<img width="457" alt="image" src="https://user-images.githubusercontent.com/82988/221201833-dc35c58e-2387-4201-a71f-b8cad33ce659.png">

Which then rebuilds things - but I don't see what has supposedly changed? Or is this just a UI issue with the Github homepage and I need to refresh the homepage after any changes to the repo???

The TM351 notebook should be running as `http://localhost:8888?token=letmein`.

It seems to take some time for the notebook server to start, but when it does, it seems to be announced:

<img width="458" alt="image" src="https://user-images.githubusercontent.com/82988/221208445-6b915f17-7fd3-4ca0-9b5b-7e6f0a5f127a.png">

To connect to the URL, search on *conn* in the VS Code command palette to find the *Jupyter: Connect to remote URL* setting.

<img width="596" alt="image" src="https://user-images.githubusercontent.com/82988/221208550-caad85e6-7a19-40d6-ac84-4f3d8c67e6b2.png">

Then paste in the above URL.

<img width="600" alt="image" src="https://user-images.githubusercontent.com/82988/221208747-20a9bf23-7096-40e9-8a33-9a30d1a66369.png">

You should then be able to connect to the *Python 3 (ipykernel) (Remote) Jupyter kernel*.

<img width="963" alt="image" src="https://user-images.githubusercontent.com/82988/221204276-b50a3a22-e0a4-43c4-8531-8f0495901beb.png">

Forwarding port 8888 seems to work okay, but I can't seem to open a new notebook and it also seems to knock the environment over:

<img width="1160" alt="image" src="https://user-images.githubusercontent.com/82988/221207565-741221ff-dd10-4c55-8ccc-0b4b2f88e535.png">

