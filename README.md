# vvmachinr
d = {
  'X': [1, 1, 1, 3, 1, 3, 1, 3, 1], 
  'Y': [0, 0, 1, 1, 1, 2, 2, 2, 1], 
  'Z': [1, 2, 2, 4, 3, 3, 1, 1, 0], 
  'Clase': ['Rojo', 'Rojo', 'Rojo', 'Rojo', 'Rojo', 'Azul', 'Azul', 'Azul', 'Azul']
}
df = pd.DataFrame(data = d)
df

X	Y	Z	Clase
0	1	0	1	Rojo
1	1	0	2	Rojo
2	1	1	2	Rojo
3	3	1	4	Rojo
4	1	1	3	Rojo
5	3	2	3	Azul
6	1	2	1	Azul
7	3	2	1	Azul
8	1	1	0	Azul
df_rojo = df[df['Clase'] == 'Rojo']
df_azul = df[df['Clase'] == 'Azul']

fig = go.Figure()

no_plot = fig.add_trace(
  go.Scatter3d(
    x = df_rojo['X'],
    y = df_rojo['Y'],
    z = df_rojo['Z'],
    mode = 'markers',
    marker = dict(size = 5, color = 'red'),
    name = 'Rojo'
  )
)

no_plot = fig.add_trace(
  go.Scatter3d(
    x = df_azul['X'],
    y = df_azul['Y'],
    z = df_azul['Z'],
    mode = 'markers',
    marker = dict(size = 5, color = 'blue'),
    name = 'Azul'
  )
)

fig

Clase Roja
P = np.array([1, 1, 2])
Q = np.array([1, 0, 1])
R = np.array([3, 1, 4])

PQ = P - Q
PR = P - R

PQ
PR

array([0, 1, 1])
array([-2,  0, -2])
ecuacion = np.cross(PQ, PR)
ecuacion

array([-2, -2,  2])
Clase Azul
P = np.array([1, 2, 1])
Q = np.array([1, 1, 0])
R = np.array([3, 2, 3])

PQ = P - Q
PR = P - R

PQ
PR

array([0, 1, 1])
array([-2,  0, -2])
ecuacion = np.cross(PQ, PR)
ecuacion

array([-2, -2,  2])
x, y = np.meshgrid(range(5), range(5))
z_rojo = x + y
z_azul = x + y - 2

no_plot = fig.add_trace(
  go.Surface(
    x = x,
    y = y,
    z = z_rojo,
    opacity = .7, 
    showscale = False, 
    colorscale = np.repeat('red', x.size, axis = 0)
  )
)

no_plot = fig.add_trace(
  go.Surface(
    x = x,
    y = y,
    z = z_azul,
    opacity = .7, 
    showscale = False, 
    colorscale = np.repeat('blue', x.size, axis = 0)
  )
)

fig


x, y = np.meshgrid(range(5), range(5))
z_optimo = x + y - 1

no_plot = fig.add_trace(
  go.Surface(
    x = x,
    y = y,
    z = z_optimo,
    opacity = .7, 
    showscale = False, 
    colorscale = np.repeat('green', x.size, axis = 0)
  )
)


fig



 
x, y = np.meshgrid(range(5), range(5))
z_no_optimo = x + y - 1/2

no_plot = fig.add_trace(
  go.Surface(
    x = x,
    y = y,
    z = z_no_optimo,
    opacity = .7, 
    showscale = False, 
    colorscale = np.repeat('yellow', x.size, axis = 0)
  )
)


fig


 
no_plot = fig.add_trace(
  go.Scatter3d(
    x = [1],
    y = [1],
    z = [4],
    mode = 'markers',
    marker = dict(size = 5, color = 'blue'),
    name = 'Azul'
  )
)


fig


⎧
​
  
−2x−2y+2z=−2
−x−y+z=−1
z=x+y−1
​



  
