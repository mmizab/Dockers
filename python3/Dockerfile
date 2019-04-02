FROM python:3
RUN pip install django djangorestframework jupyter
# mount the src volume here
WORKDIR /frontend
EXPOSE 8888
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--allow-root"]
