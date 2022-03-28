import { useEffect, useState } from "react"

const Listado = () => {
  //se definen las variables a cambiar
  const [equipo, setequipos] = useState([])

  useEffect(() => {
    //variable donde se guardara la informacion del fetch y se ejecuta

    obtenerdata()
  }, [])

  const obtenerdata = async () => {
    const data = await fetch("https://jsonplaceholder.typicode.com/users")
    const users = await data.json()
    setequipos(users)
  }
  return (
    <div>
      <div className="container">
        <h2>Listado de Usuarios</h2>
        <ul>
          {equipo.map((item) => (
            <li key={item.id}>
              Username: {item.username} - {item.name} - {item.email}
            </li>
          ))}
        </ul>
      </div>
    </div>
  )
}

export default Listado
