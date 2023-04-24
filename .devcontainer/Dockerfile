FROM ouvocl/vce-tm351-jh:22j-b6

USER root
RUN sed -i 's/  "python",/  "python3",/g' /usr/local/share/jupyter/kernels/python3/kernel.json

USER $NB_USER
