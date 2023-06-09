# NVIDIA Audio2Face to Unreal Engine 5 (Metahumans) import script
Alternative way to import an audio2face facial animation to unreal engine 5 (for use in metahumans).

I have been in the situation that I have a bunch of Linux servers where NVIDIA's Audio to face and Unreal Engine runs in a docker containers and got the creation of face animations up and running (following, for example, this tutorial on YouTube: https://www.youtube.com/watch?v=x9POZqGO5B0). 
However, the NVIDIA Omniverse Plugin used to import the animation is not distributed for Linux, and the Plugin also has around 50k lines of code and you have to wait for it's availability on every new version of UE5. 
Thus, I read the source code and wrote a short python script for the use case of importing just the *.usd(a) facial animation. 
It's shared as the following gist: https://gist.github.com/Johann-Foerster/c6dc45fb2ee7a28c081ea78042f225f5. 

You have to specify your path to the USD on the disk as well as the output asset's path. 

Since I found no way to change the skeleton of an AnimSequence object in python (as of UE 5.1), I just duplicate an existing animation and fill it with data. The distributed animation in EXAMPLE_ANIMATION_REFERENCE defaults to 24fps, however. You may also use the 60fps .uasset in this repo. 

Blueprint block for copy-paste: https://blueprintue.com/blueprint/xdaswvsj/

Result: 50 lines of code instead of 50k. Hope this helps someone :)
