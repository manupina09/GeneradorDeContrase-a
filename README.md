# GeneradorDeContrase-a
Estructra de datos Atc.2
import re
import secrets
import string

def generar_contraseña (longitud, nums, caracateres_especiales, mayusculas, minusculas): 
    
    letras = string.ascii_letters
    digitos = string.digits
    simbolos = string.punctuation
    
    todos_los_caracteres = letras + digitos + simbolos
    
    while true: 
        contraseña = '' 
        for _ in range (longitud):
            contraseña += secrets.choice(todos_los_caracteres)
            
            restricciones = [
                (nums, r'\d' ),
                (minusculas, r'[a-z]'),
                (mayusculas, r'[A-Z]'),
                (caracteres_especiales, fr'[{simbolos}]')
                ]
                
                count = 0 
                for restriccion, patron in restricciones:
                    if restriccion <= len(re.findall(patron, contraseña)):
                        += 1 
                    if count == 4: 
                        break 
                    return contraseña
                    
nueva_contraseña = generar_contraseña (8, 2, 2, 2, 2)
print (nueva_contraseña)
