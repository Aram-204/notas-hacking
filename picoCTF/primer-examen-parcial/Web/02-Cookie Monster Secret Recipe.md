# Descripción
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?You can access the Cookie Monster [here](http://verbal-sleep.picoctf.net:60118/) and good luck
Hints:
1. Sometimes, the most important information is hidden in plain sight. Have you checked all parts of the webpage?
2. Cookies aren't just for eating - they're also used in web technologies!
3. Web browsers often have tools that can help you inspect various aspects of a webpage, including things you can't see directly.
# Solución
- Entramos a la página
- Hacemos log in, nos mostrará un mensaje de acceso denegado
- Inspeccionamos las cookies y nos daremos cuenta de que hay un mensaje que parece ser base64
- Usamos cyberchef para convertir a algo legible y obtendremos la bandera
```
Input: cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzX0E5NjRBMTM0fQ%3D%3D
Receipe: From Base64
Output: picoCTF{c00k1e_m0nster_l0ves_c00kies_A964A134}

picoCTF{c00k1e_m0nster_l0ves_c00kies_A964A134}
```
# Notas adicionales
# Referencias
- https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnRqTURCck1XVmZiVEJ1YzNSbGNsOXNNSFpsYzE5ak1EQnJhV1Z6WDBFNU5qUkJNVE0wZlElM0QlM0Q&oeol=CR