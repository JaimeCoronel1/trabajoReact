¿Qué es React Router y para qué se utiliza?
React Router es una biblioteca que permite crear navegación entre diferentes vistas o páginas dentro de una aplicación React sin recargar la página (SPA: Single Page Application).

📌 Se utiliza para:

Crear rutas (URLs) como /home, /about, /producto/23

Navegar entre componentes según la URL

Redirigir usuarios

Mostrar u ocultar contenido según la ruta

¿Cuál es la diferencia entre <BrowserRouter>, <Routes>, <Route> y <Link>?
Elemento	Descripción breve
<BrowserRouter>	Componente que envuelve toda la app. Habilita la navegación basada en URLs.
<Routes>	Contenedor para todas las rutas definidas. Reemplaza al viejo <Switch>.
<Route>	Define una ruta específica, por ejemplo: <Route path="/about" element={<About />} />
<Link>	Enlace para navegar entre rutas sin recargar la página. Reemplaza al <a href="">.

¿Qué es un componente de ruta?
Un componente de ruta es un componente que se muestra cuando la URL coincide con una ruta definida en <Route>.

Por ejemplo, si tienes:

jsx
Copiar
Editar
<Route path="/contact" element={<Contact />} />
Entonces <Contact /> es un componente de ruta, que se renderiza cuando el usuario va a http://localhost:3000/contact.

Cómo se configuran rutas dinámicas?
Las rutas dinámicas permiten capturar valores variables en la URL.

🧱 Ejemplo de definición:

jsx
Copiar
Editar
<Route path="/producto/:id" element={<Producto />} />
📌 En este caso, /producto/5 o /producto/abc son rutas válidas, y puedes acceder al valor id usando useParams():

jsx
Copiar
Editar
import { useParams } from "react-router-dom";

function Producto() {
  const { id } = useParams();
  return <h1>Producto con ID: {id}</h1>;
}

¿Qué es useNavigate y cómo se usa para redirigir?
useNavigate es un hook de React Router que se usa para navegar programáticamente desde el código.

🧱 Ejemplo de uso:

jsx
Copiar
Editar
import { useNavigate } from "react-router-dom";

function Home() {
  const navigate = useNavigate();

  const irAContacto = () => {
    navigate("/contact");
  };

  return <button onClick={irAContacto}>Ir a Contacto</button>;
}
