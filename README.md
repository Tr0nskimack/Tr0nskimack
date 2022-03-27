import React, { useState, useEffect } from "react"

const Listado = () => {
  //se definen las variables a cambiar
  const [equipo, setequipos] = useState()

  useEffect(() => {
    //variable donde se guardara la informacion
    obtenerdata()
  }, [])

  const obtenerdata = async () => {
    const data = await fetch("https://jsonplaceholder.typicode.com/users")
    const users = await data.json()
    setequipos(users)
  }
  return (
    <div>
      <h2>Listado de Usuarios</h2>
    </div>
  )
}

export default Listado
