---
sticker: lucide//file-warning
---

# Caso 1

Asegúrate de que todo esta en la carpeta raíz , ya que busca por ruta relativa, como indica en [[01_Configuracion#Configuración Directorios|Configuración de directorios]] 



![[directorioRaiz.png]]

las tres carpetas están las mismo nivel, al igual que tsconfig.json.


# Caso 2

![[error-debug-policy.png]]


este error viene ya comentado en [[00_Instalacion#Error en paso 2|Error de instalación]], se soluciona abriendo powershell como administrador y poner el comando:  

`                            Set-ExecutionPolicy Unrestricted                               `

encontrado en [stackoverflow](https://es.stackoverflow.com/questions/321611/problema-con-scripts-en-visual-studio-code)

![[solucionPolicyUnrestricted.png]]