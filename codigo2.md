print(" puga fernandez jorge kaled")
print(" ")
def crear_diccionario():
    """Crea un diccionario de traducción a partir de la entrada del usuario."""
    diccionario = {"hola":"hello"}
    entrada = input("Introduce las traducciones (formato: español:inglés, ...): ")
    
    for par in entrada.split(","):
        try:
            esp, ing = map(str.strip, par.split(":"))
            diccionario[esp] = ing
        except ValueError:
            print(f"Entrada inválida: '{par}'. Asegúrate de usar el formato correcto.")
    
    return diccionario

def traducir_frase(diccionario):
    """Traduce una frase palabra por palabra utilizando el diccionario."""
    frase = input("Introduce una frase en español: ")
    palabras = frase.split()
    traduccion = []
    
    for palabra in palabras:
        traduccion.append(diccionario.get(palabra, palabra))  # Traducir o dejar sin ff
    
    return " ".join(traduccion)

def main():
    """Función principal que ejecuta el programa de traducción."""
    print("Bienvenido al traductor español-inglés.")
    diccionario = crear_diccionario()  # Crear el diccionario de traducción
    
    while True:
        frase_traducida = traducir_frase(diccionario)  # Traducir la frase ingresada
        print("Frase traducida:", frase_traducida)  # Mostrar el resultado
        
        continuar = input("¿Quieres traducir otra frase? (s/n): ").lower()
        if continuar != 's':
            print("Gracias por usar el traductor. ¡Hasta luego!")
            break

if __name__ == "__main__":
    main()
![image](https://github.com/user-attachments/assets/1612ca9e-5c96-46a1-a211-2d0e1bc30bf2)
![image](https://github.com/user-attachments/assets/7da885c6-7d9c-4703-b0d4-98c8cc12a6d9)
