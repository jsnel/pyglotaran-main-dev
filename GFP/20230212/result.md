| Optimization Result                       |          |
|-------------------------------------------|----------|
| Number of residual evaluation             | 11       |
| Number of residuals                       | 32160    |
| Number of free parameters                 | 7        |
| Number of conditionally linear parameters | 960      |
| Degrees of freedom                        | 31193    |
| Chi Square                                | 6.39e+03 |
| Reduced Chi Square                        | 2.05e-01 |
| Root Mean Square Error (RMSE)             | 4.52e-01 |

# Model

## Clp Relations

- **&nbsp;**
  - _Interval_: [[0, 1000]]
  - _Source_: A1
  - _Target_: A2
  - _Parameter_: rel.r1(1.00e+00, fixed)


## Dataset Groups

- **default**
  - _Label_: default
  - _Residual Function_: variable_projection


## K Matrix

- **k1**
  - _Label_: k1
  - _Matrix_: {('I', 'A2'): 'kinetic.to_I_from_A2(7.67e-02±8.82e-04, t-value: 87, initial: 8.00e-02)', ('I', 'A1'): 'kinetic.to_I_from_A1(3.50e-01±3.67e-03, t-value: 96, initial: 4.00e-01)', ('I2', 'I'): 'kinetic.to_I2_from_I(3.35e-04, fixed)', ('I2', 'I2'): 'kinetic.from_I2(2.53e-03, fixed)'}


## Megacomplex

- **decay**
  - _Label_: decay
  - _Dimension_: time
  - _Type_: decay
  - _K Matrix_: ['k1']

- **artifact**
  - _Label_: artifact
  - _Dimension_: time
  - _Type_: coherent-artifact
  - _Order_: 1


## Initial Concentration

- **j1**
  - _Label_: j1
  - _Compartments_: ['A2', 'A1', 'I2', 'I']
  - _Parameters_: ['j.2(4.21e-01±5.19e-03, t-value: 81, initial: 5.00e-01)', 'j.1(5.79e-01=1-_j.2(4.21e-01±5.19e-03, t-value: 81)_)', 'j.0(0.00e+00, fixed)', 'j.0(0.00e+00, fixed)']
  - _Exclude From Normalize_: []


## Irf

- **irf1**
  - _Label_: irf1
  - _Normalize_: True
  - _Backsweep_: False
  - _Dispersion Center_: irf.dispcenter(5.00e+02, fixed)
  - _Center Dispersion Coefficients_: ['irf.disp1(-2.78e-01±9.22e-03, t-value: -30, initial: -3.27e-01)', 'irf.disp2(-2.37e-01±9.24e-03, t-value: -26, initial: -1.92e-01)']
  - _Width Dispersion Coefficients_: []
  - _Model Dispersion With Wavenumber_: True
  - _Type_: spectral-gaussian
  - _Center_: irf.center(3.48e-01±1.99e-03, t-value: 175, initial: 3.60e-02)
  - _Width_: irf.width(6.70e-02±5.24e-04, t-value: 128, initial: 8.33e-02)


## Dataset

- **GFPppH2O**
  - _Label_: GFPppH2O
  - _Group_: default
  - _Force Index Dependent_: False
  - _Megacomplex_: ['decay', 'artifact']
  - _Initial Concentration_: j1
  - _Irf_: irf1


