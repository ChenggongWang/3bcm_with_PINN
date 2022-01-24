# 3bcm_with_PINN
Use Physics Informed Neural Networks (PINN) to 
- fit the 3-box climate model (3bcm)
- learn climate parameters (e.g. climate feedbacks, ocean heat uptake rate and efficacy)
- predict outside the data range.

## Physics Informed Neural Networks (PINN)
The work is built based on the example of Navier-Stokes Equation in [PINN](https://github.com/maziarraissi/PINNs). To use NN learns (fits) the data and the physical model in the same time, we need to construct the loss function not only with traditional data loss, but also the function loss. So, the trained NN satisfies the data and the physics in the same time. For more details, please reference: https://maziarraissi.github.io/PINNs/.

## 3-box climate model:
The simple box model used to emulate GCM is described by following equations:
<img src="https://render.githubusercontent.com/render/math?math=\color{grey50}
C_s\frac{dT_s}{dt} &=  F_s + \lambda_s T_s - \epsilon_s\gamma_s (T_s-T_d) + Q (T_n - T_s) \\
C_n\frac{dT_n}{dt} &=  F_n + \lambda_n T_n - \epsilon_n\gamma_n (T_n-T_d) - Q (T_n - T_s) \\
C_d\frac{dT_d}{dt} &=  \gamma_s (T_s-T_d) + \gamma_n (T_n-T_d)">

## Training data
The temperature and TOA radiation flux data of abrupt-4xCO2 experiment preformed by GFDL-CM4 are prepocessed and save as NH and SH mean in file: [temp_data_TN_NS_np.p].


![image](https://user-images.githubusercontent.com/61756907/150723100-61001d3e-f624-4f46-8980-020753ccaddf.png)

# 
