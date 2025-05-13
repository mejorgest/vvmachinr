# vvmachinr

d = {
  'X': [1, 1, 1, 3, 1, 3, 1, 3, 1], 
  'Y': [0, 0, 1, 1, 1, 2, 2, 2, 1], 
  'Z': [1, 2, 2, 4, 3, 3, 1, 1, 0], 
  'Clase': ['Rojo', 'Rojo', 'Rojo', 'Rojo', 'Rojo', 'Azul', 'Azul', 'Azul', 'Azul']
}
df = pd.DataFrame(data = d)
df

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



P = np.array([1, 1, 2])
Q = np.array([1, 0, 1])
R = np.array([3, 1, 4])

PQ = P - Q
PR = P - R

PQ
PR


ecuacion = np.cross(PQ, PR)
ecuacion


P = np.array([1, 2, 1])
Q = np.array([1, 1, 0])
R = np.array([3, 2, 3])

PQ = P - Q
PR = P - R

PQ
PR


ecuacion = np.cross(PQ, PR)
ecuacion


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







  
