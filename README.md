# cmodel
Caffe-like explicit model constructor. C(onfig)Model

# Installation
`pip install git+https://github.com/bonlime/cmodel`

# Usage
In order to allow using your own modules you have to redefine `CModel.eval` after imports. Example:

```python
from mypackage.modules import MyModule
from cmodel import CModel as OriginalCModel

class CModel(OriginalCModel):
    @staticmethod
    def eval(name):
        return eval(name)

# now you could use `MyModule` in your configs
```