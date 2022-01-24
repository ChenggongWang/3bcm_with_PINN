# 3bcm_with_PINN
Use Physics Informed Neural Networks (PINN) to 
- fit the 3-box climate model (3bcm)
- learn climate parameters (e.g. climate feedbacks, ocean heat uptake rate and efficacy)
- learn hidden varaibles: deep ocean change
- predict outside the data range.

The figure below summarize the resluts. We train the PINN with data in year 0-150 and function in year 0-250. Solid lines are the output values in year 0-400 from PINN. It is clearly that the PINN did a reasonably good job in year 150-250, which is outside of the train data but constrianed by function . For the output outside the data and the function range (year 250-400), it begins to be wild. 

![image](https://user-images.githubusercontent.com/61756907/150723100-61001d3e-f624-4f46-8980-020753ccaddf.png)
![download](https://user-images.githubusercontent.com/61756907/150727067-aaaea3a0-fd55-4da7-8acd-e28c308925a2.jpeg)

## Physics Informed Neural Networks (PINN)
The work is built based on the example of Navier-Stokes Equation in [PINN](https://github.com/maziarraissi/PINNs). To use NN learns (fits) the data and the physical model in the same time, we need to construct the loss function not only with traditional data loss, but also the function loss. So, the trained NN satisfies the data and the physics in the same time. For more details, please reference: https://maziarraissi.github.io/PINNs/.

## 3-box climate model:
The simple box model used to emulate GCM is described by following equations:
![image](https://user-images.githubusercontent.com/61756907/150725892-34335398-e1af-40e1-a226-5945df14dc7d.png)

![image](https://user-images.githubusercontent.com/61756907/150725909-dab6f6be-0126-471d-8f3e-00e6af23343f.png)

Known variables: T_n, T_s, N_n, N_s.
Unknown variables: T_d
Unknown parameters: ![image](https://user-images.githubusercontent.com/61756907/150726984-e7943291-3987-467a-9e6d-df7f87e909cf.png)

## Training data
The temperature and TOA radiation flux data of abrupt-4xCO2 experiment preformed by GFDL-CM4 are prepocessed and save as NH and SH mean in file: [temp_data_TN_NS_np.p].


