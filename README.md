**DirectDM**: a python package for dark matter direct detection
=====

`directdm` takes the Wilson coefficients of relativistic operators that couple DM to the SM quarks, leptons, and gauge bosons and matches them onto a non-relativistic Galilean invariant EFT in order to calculate the direct detection scattering rates.

You can get the latest version of `directdm` on [`github`](https://directdm.github.io).

## Installation

`directdm` needs `python3`, and the `python3` versions of `SciPy` and `NumPy`.

After cloning this repository, you can easily install `directdm` by using the `python3` version of `pip`. In the base directory of the package, execute

```
python3 setup.py sdist
pip install dist/directdm-1.0.0.tar.gz
```

(You might need root permissions to execute the second command, 
and `pip` might be called `pip3` on your system.)

**Note**: the package has been tested on a linux machine. Mac users using `homebrew` should be able to install `directdm` after executing

```
brew install python3
brew upgrade numpy
brew upgrade scipy
```

## Usage

The included `example.py` file has basic examples for using the functions provided by the code. 

Here is a simple example how to use `directdm`:

Load the package
```
import directdm as ddm
```

Define some Wilson coefficients for Dirac DM in the three-flavor basis, using a `python` dictionary:
```
wc_dict = {'C61u' : 1./100**2 , 'C61d' : 1./100**2}
wc3f = ddm.WC_3f(wc_dict, DM_type="D")
```

Match the three-flavor Wilson coefficients onto the non-relativstic ones (the DM mass has been set to 100 GeV, and the momentum transfer is 50 MeV):
```
print(wc3f.cNR(100, 50e-3))
```

Write the list of proton and neutron NR Wilson coefficients into a file in the current directory with filename 'wc3.m':
```
wc3f.write_mma(100, 50e-3, filename='wc3.m')
```

## Citation
If you use `DirectDM` please cite us! To get the `BibTeX` entries, click on: [inspirehep query](https://inspirehep.net/search?p=arxiv:1708.02678+or+arxiv:1707.06998+or+arxiv:1611.00368&of=hx) 


## Main Author 

   * Joachim Brod (TU Dortmund)


## Contributors

   * Fady Bishara (University of Oxford)
   * Jure Zupan (University of Cincinnati)
   * Benjamin Grinstein (UC San Diego)


## License
`DirectDM` is distributed under the MIT license.


[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
