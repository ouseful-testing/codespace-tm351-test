# codespace-tm351-test
*Test TM351 container in codespace*

This repo demonstrates settings for running an OU built Docker container inside Github Codespace.

Create a workspace:

<img width="410" alt="image" src="https://user-images.githubusercontent.com/82988/221218040-ae9aaa06-5854-405e-8e11-6ecaa45f37ea.png">

On first creating the workspace, the TM351 Docker image will be downloaded and a container spawned from it.

By default, the environment opens into a VS Code editor (is there a way of changing that via a config setting so that it opens in JupyerLab?)

For some reason, something changes, and I get prompted to rebuild:

<img width="457" alt="image" src="https://user-images.githubusercontent.com/82988/221201833-dc35c58e-2387-4201-a71f-b8cad33ce659.png">

(I'm not sure if this is due to some cruft that has been cached from a previous session?)

Notebooks can be opened using the default VSCode editor.

I keep seeming to hit inconsistent behaviour trying to connect to the kernel.

When deleting and relaunching the workspace, I often seem to get:

Which then rebuilds things - but I don't see what has supposedly changed? Or is this just a UI issue with the Github homepage and I need to refresh the homepage after any changes to the repo???

I'm not sure if I have to forward the port?

<img width="835" alt="image" src="https://user-images.githubusercontent.com/82988/221220472-d67e518c-f188-46c7-8950-645847a1b160.png">


The TM351 notebook should be running as `http://localhost:8888?token=letmein`.

The notebook server seems to take some time to start. Sometimes (I'm not sure under what conditions), it seems to be announced:

<img width="458" alt="image" src="https://user-images.githubusercontent.com/82988/221208445-6b915f17-7fd3-4ca0-9b5b-7e6f0a5f127a.png">

To connect to the URL, search on *conn* in the VS Code command palette to find the *Jupyter: Connect to remote URL* setting.

<img width="596" alt="image" src="https://user-images.githubusercontent.com/82988/221208550-caad85e6-7a19-40d6-ac84-4f3d8c67e6b2.png">

Then paste in the above URL.

<img width="600" alt="image" src="https://user-images.githubusercontent.com/82988/221208747-20a9bf23-7096-40e9-8a33-9a30d1a66369.png">

You should then be able to connect to the *Python 3 (ipykernel)*(Remote) Jupyter kernel*.

NOTE: at other times, I seem to be able to connect just to *Python 3 (ipykernel)*, eg if I restart the workspace. There is something going on in the plumbing, almost as if the kernel is picked up by default, but not the token?  It would be useful to be able to set up the kernel URL connection etc in a `.devcontainer` settings file.

<img width="963" alt="image" src="https://user-images.githubusercontent.com/82988/221204276-b50a3a22-e0a4-43c4-8531-8f0495901beb.png">

Displaying the notebook homepage (or JupyterLab UI) via the forwarded port 8888 seems to work okay, but I can't seem to open a new notebook (which also seems to knock the environment over):

<img width="1160" alt="image" src="https://user-images.githubusercontent.com/82988/221207565-741221ff-dd10-4c55-8ccc-0b4b2f88e535.png">

If I stop the workspace, and then restart/repopen it, I looks like I can reopen it into a JupyterLab UI rather than the VS Code UI (can I pre-install extensions into th JupyterLab UI via a settings file?)

<img width="459" alt="image" src="https://user-images.githubusercontent.com/82988/221222044-7cbe2fca-fdd4-42f2-abfe-6f7822ffe986.png">

<img width="326" alt="image" src="https://user-images.githubusercontent.com/82988/221222102-7b2ca4f8-52cf-47ca-ac1a-64f2e57716bf.png">

Or not:

<img width="1042" alt="image" src="https://user-images.githubusercontent.com/82988/221222577-8fcc013c-0700-499c-9edc-b85d6502f718.png">

Try again, this time with the codespace running from the previoulsy failed attempt to open it in JupyterLab:

<img width="1010" alt="image" src="https://user-images.githubusercontent.com/82988/221223021-d1303c03-f6d9-48d4-9e33-23ba3179328d.png">

Hmmm... I notice that the server extensions have been picked up (Open Refine and nbsearch).

And they run:

<img width="916" alt="image" src="https://user-images.githubusercontent.com/82988/221223400-0ff7fc57-b585-4932-b40f-978f6405367b.png">

And the correct kernel seems to be available; for example, the databases are connecting fine...

<img width="892" alt="image" src="https://user-images.githubusercontent.com/82988/221223732-b6919975-b6f7-4fe1-a4c1-9a24691662a0.png">

But then I try again...

<img width="725" alt="image" src="https://user-images.githubusercontent.com/82988/221226514-57cffdb9-c1c3-4b08-886f-c914b8bcb736.png">


__At this point, I get the feeling that this is not really viable - the current setup/recipe above seems a bit fraught and hacky, but we can get to a working JupyterLab instance. It'd be nice to have a robust set of instructions that work reliably, and also to find a way customise the JupyerLab environment (or is it somehow picking up the JupyterLab environment in the container???). I'm also not sure I've got a good model of how the CodeSpace actually works...__
