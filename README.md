# Mostrar-la-tabla-de-resultados-de-conductores-en-un-TablaView

![Capture1](https://github.com/josesamaniego14/Mostrar-la-tabla-de-resultados-de-conductores-en-un-TablaView/assets/169215284/f6bb75a3-723f-4288-8cc8-4993bba011e2)

![Capture2](https://github.com/josesamaniego14/Mostrar-la-tabla-de-resultados-de-conductores-en-un-TablaView/assets/169215284/81100fc8-461f-4043-84b6-668e5a37aa49)

La clase InterfazGrafica crea una interfaz gráfica utilizando Swing para mostrar información de conductores de Fórmula 1 de una base de datos PostgreSQL. La interfaz permite seleccionar un año de carrera y muestra una tabla con los conductores que participaron en las carreras de ese año, junto con estadísticas como el número de carreras y el número de carreras ganadas.

Componentes Principales

Variables de Clase
Connection conn: Conexión a la base de datos PostgreSQL.
JFrame frame: Ventana principal de la interfaz gráfica.
JComboBox<String> comboBox: Combo box para seleccionar el año de carrera.
JTable table: Tabla para mostrar los datos de los conductores.
DefaultTableModel tableModel: Modelo de datos para la tabla.

Constructor InterfazGrafica
Llama a connectDB para establecer la conexión a la base de datos.
Llama a createGUI para crear la interfaz gráfica.

Método connectDB
Establece la conexión a la base de datos PostgreSQL utilizando DriverManager.getConnection.
Maneja excepciones de SQL (SQLException).

Método createGUI
Configura el JFrame para la ventana principal.
Crea y configura el JComboBox para seleccionar el año de carrera.
Llama a populateComboBox para llenar el combo box con los años disponibles en la base de datos.
Crea y configura el JTable y su modelo (DefaultTableModel).
Añade el combo box y la tabla al JFrame y lo hace visible.

Método populateComboBox
Ejecuta una consulta SQL para obtener los años de las carreras desde la base de datos y los añade al combo box.

Método updateTable
Se llama cuando se selecciona un año en el combo box.
Ejecuta una consulta SQL para obtener los datos de los conductores que participaron en las carreras del año seleccionado.
Actualiza el modelo de datos de la tabla (tableModel) con los resultados de la consulta.

Método main
Llama a SwingUtilities.invokeLater para asegurar que la interfaz gráfica se construya y se actualice en el hilo de despacho de eventos de Swing.

Funcionamiento
Al iniciar la aplicación, se establece una conexión con la base de datos PostgreSQL.
La ventana principal (JFrame) se configura y se muestra.
El combo box se llena con los años de las carreras disponibles en la base de datos.
Al seleccionar un año en el combo box, se ejecuta una consulta SQL para obtener los datos de los conductores de ese año y se actualiza la tabla.
Este diseño permite una interfaz gráfica interactiva donde el usuario puede seleccionar diferentes años y ver la información correspondiente de los conductores en una tabla bien estructurada.
