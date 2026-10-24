import tkinter as tk

def unidades():
    precio = float(precio_costo.get())
    variable = float(costo_variable.get())
    fijo = float(costo_fijo.get())

    unidades_eq = fijo / (precio - variable)
    quetzales_eq = fijo / ((precio - variable) / precio)

    pe_unidades.config(text=f"{unidades_eq:.2f} unidades")
    pe_quetzales.config(text=f"Q {quetzales_eq:.2f}")


def grafica():
    precio = float(precio_costo.get())
    variable = float(costo_variable.get())
    fijo = float(costo_fijo.get())

    pe = fijo / (precio - variable)
    maximo = pe * 2
    y_max = maximo * precio

    lienzo.delete("all")

    ancho = 650
    alto = 340
    izq = 80
    der = ancho - 20
    arriba = 30
    abajo = alto - 55

    def px(x):
        return izq + (x / maximo) * (der - izq)

    def py(y):
        return abajo - (y / y_max) * (abajo - arriba)

    lienzo.create_line(izq, arriba, izq, abajo, width=2)
    lienzo.create_line(izq, abajo, der, abajo, width=2)

    for i in range(6):
        valor_x = maximo * i / 5
        valor_y = y_max * i / 5

        lienzo.create_line(px(valor_x), abajo, px(valor_x), abajo + 5)
        lienzo.create_text(px(valor_x), abajo + 15, text=f"{valor_x:.0f}",
                           font=("Verdana", 8))

        lienzo.create_line(izq - 5, py(valor_y), izq, py(valor_y))
        lienzo.create_text(izq - 8, py(valor_y), text=f"{valor_y:.0f}",
                           anchor="e", font=("Verdana", 8))

    lienzo.create_text((izq + der) / 2, alto - 15, text="Unidades vendidas",
                       font=("Verdana", 10, "bold"))
    lienzo.create_text(15, (arriba + abajo) / 2, text="Quetzales (Q)",
                       angle=90, font=("Verdana", 10, "bold"))

    lienzo.create_line(px(0), py(0), px(maximo), py(maximo * precio), fill="green", width=3)
    lienzo.create_line(px(0), py(fijo), px(maximo), py(fijo + variable * maximo), fill="red", width=3)
    lienzo.create_line(px(0), py(0), px(maximo), py(variable * maximo), fill="orange", width=3)
    lienzo.create_line(px(0), py(fijo), px(maximo), py(fijo), fill="blue", width=3)

    x_pe = px(pe)
    y_pe = py(pe * precio)
    lienzo.create_oval(x_pe - 5, y_pe - 5, x_pe + 5, y_pe + 5, fill="black")


ventana = tk.Tk()
ventana.title("Calculadora de Punto de Equilibrio")
ventana.geometry("700x720")
ventana.config(bg="#1e1e2f")

titulo = tk.Label(ventana, text="PUNTO DE EQUILIBRIO",
                  font=("Verdana", 20, "bold"), bg="#1e1e2f", fg="#f9c74f")
titulo.pack(pady=15)

cuadro_datos = tk.Frame(ventana, bg="#2d2d44", padx=20, pady=15)
cuadro_datos.pack(pady=5)

tk.Label(cuadro_datos, text="Precio de venta:", font=("Verdana", 11),
         bg="#2d2d44", fg="white").grid(row=0, column=0, sticky="e", pady=5)
precio_costo = tk.Entry(cuadro_datos, font=("Verdana", 11), width=15, justify="center")
precio_costo.grid(row=0, column=1, padx=10)

tk.Label(cuadro_datos, text="Costos variables:", font=("Verdana", 11),
         bg="#2d2d44", fg="white").grid(row=1, column=0, sticky="e", pady=5)
costo_variable = tk.Entry(cuadro_datos, font=("Verdana", 11), width=15, justify="center")
costo_variable.grid(row=1, column=1, padx=10)

tk.Label(cuadro_datos, text="Costos fijos:", font=("Verdana", 11),
         bg="#2d2d44", fg="white").grid(row=2, column=0, sticky="e", pady=5)
costo_fijo = tk.Entry(cuadro_datos, font=("Verdana", 11), width=15, justify="center")
costo_fijo.grid(row=2, column=1, padx=10)

cuadro_botones = tk.Frame(ventana, bg="#1e1e2f")
cuadro_botones.pack(pady=10)

boton = tk.Button(cuadro_botones, text="Calcular", font=("Verdana", 11, "bold"),
                  bg="#43aa8b", fg="white", width=12, command=unidades)
boton.grid(row=0, column=0, padx=10)

boton_grafica = tk.Button(cuadro_botones, text="Graficar", font=("Verdana", 11, "bold"),
                          bg="#f94144", fg="white", width=12, command=grafica)
boton_grafica.grid(row=0, column=1, padx=10)

cuadro_result = tk.Frame(ventana, bg="#2d2d44", padx=20, pady=10)
cuadro_result.pack(pady=5)

tk.Label(cuadro_result, text="Unidades de equilibrio:", font=("Verdana", 11),
         bg="#2d2d44", fg="white").grid(row=0, column=0, sticky="e")
pe_unidades = tk.Label(cuadro_result, text="", font=("Verdana", 11, "bold"),
                       bg="#2d2d44", fg="#90be6d", width=18)
pe_unidades.grid(row=0, column=1)

tk.Label(cuadro_result, text="Ventas de equilibrio:", font=("Verdana", 11),
         bg="#2d2d44", fg="white").grid(row=1, column=0, sticky="e")
pe_quetzales = tk.Label(cuadro_result, text="", font=("Verdana", 11, "bold"),
                        bg="#2d2d44", fg="#90be6d", width=18)
pe_quetzales.grid(row=1, column=1)

lienzo = tk.Canvas(ventana, width=650, height=340, bg="white")
lienzo.pack(pady=15)

ventana.mainloop()