import numpy as np
import matplotlib.pyplot as plt

force_x1 = -3.99e-10  # Olivine (N)
mass1 = 1.7e-9  # Olivine (kg)

force_x2 = -1.09e-12  # Ilmeninte (N)
mass2 = 1e-9  # Ilmeninte (kg)
g_moon = 1.62  

# Intialize
x0 = 0.0
y0 = 100.0
vx0 = 0.0
vy0 = 0.0 
x0_cm = x0 * 100  
y0_cm = y0 * 100 

dt = 0.00001  # Steps
t_max = 10  # Simulation time

t_values = np.arange(0, t_max, dt)
x_values1 = np.zeros_like(t_values)
y_values1 = np.zeros_like(t_values)
vx_values1 = np.zeros_like(t_values)
vy_values1 = np.zeros_like(t_values)

x_values2 = np.zeros_like(t_values)
y_values2 = np.zeros_like(t_values)
vx_values2 = np.zeros_like(t_values)
vy_values2 = np.zeros_like(t_values)

x_values1[0] = x0_cm
y_values1[0] = y0_cm
vx_values1[0] = vx0
vy_values1[0] = vy0

x_values2[0] = x0_cm
y_values2[0] = y0_cm
vx_values2[0] = vx0
vy_values2[0] = vy0

for i in range(1, len(t_values)):
    vx_values1[i] = vx_values1[i-1] + (force_x1 / mass1) * dt
    vy_values1[i] = vy_values1[i-1] - g_moon * dt
    x_values1[i] = x_values1[i-1] + vx_values1[i] * dt
    y_values1[i] = y_values1[i-1] + vy_values1[i] * dt

for i in range(1, len(t_values)):
    vx_values2[i] = vx_values2[i-1] + (force_x2 / mass2) * dt
    vy_values2[i] = vy_values2[i-1] - g_moon * dt 
    x_values2[i] = x_values2[i-1] + vx_values2[i] * dt
    y_values2[i] = y_values2[i-1] + vy_values2[i] * dt

# Convert to meters
x_values1_m = x_values1 / 100
y_values1_m = y_values1 / 100
x_values2_m = x_values2 / 100
y_values2_m = y_values2 / 100

# Plot trajectories
plt.figure(figsize=(8, 6))
plt.plot(x_values1_m, y_values1_m, label='Particle 1 (Olivine)')
plt.plot(x_values2_m, y_values2_m, label='Particle 2 (Ilmeninte)')
plt.title('Trajectories of Particles during electrostatic separation')
plt.xlabel('Horizontal Position (m)')
plt.ylabel('Vertical Position (m)')
plt.legend()
plt.grid(True)
plt.show()
