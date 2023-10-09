Dataset **HRSC2016-MS** can be downloaded in [Supervisely format](https://developer.supervisely.com/api-references/supervisely-annotation-json-format):

 [Download](https://assets.supervisely.com/supervisely-supervisely-assets-public/teams_storage/c/r/nK/1PvztFeWJENycfrbR3WiaCVaRC88H13ceaU6VFExuF0uPDJtk7dhCVLKHad7ydJ6D4FzjB5KX6HeTGOeILCC7TTQFwU2RCJZO7nGdlxOI3D8JHMWfWuY0iVTddiD.tar)

As an alternative, it can be downloaded with *dataset-tools* package:
``` bash
pip install --upgrade dataset-tools
```

... using following python code:
``` python
import dataset_tools as dtools

dtools.download(dataset='HRSC2016-MS', dst_dir='~/dataset-ninja/')
```
Make sure not to overlook the [python code example](https://developer.supervisely.com/getting-started/python-sdk-tutorials/iterate-over-a-local-project) available on the Supervisely Developer Portal. It will give you a clear idea of how to effortlessly work with the downloaded dataset.

