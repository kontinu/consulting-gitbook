# CI - Hypothetic Case

De nuevo planteamos el [ejemplo visto en la seccion de Devops](../devops/devops/devops-hypothetic-case.md).

Se contacta via correo electronico al equipo de desarrollo `[Mie 2:00 pm]` el cual  luego de un par de horas revisa su correo y despues de prueba y error logra "corregir" el error. 

```text
# index.html
<h1>
Mi página de Productos:
</h1>

<ul>
<li> <h2> Producto 1 </h2></li>
<li> <h2> Producto 2 </h2></li>
<li> <h2> Producto 3 </h2></li>
<li> <h2> Producto 4 </h2></li>
 
<li> <h2> Producto con eror </h2></li>
</ul>
```

> ¿ nota cómo hace falta un `r` dentro de la palabra `eror` ?

 

El desarrollador integra su nuevo cambio `[Mie 4:25 pm]` creyendo que este soluciona el problema del typo; Una vez hecho se inicia todo el proceso burocratico o tecnico para cualquier cambio realizado en su ambiente de **produccion:**

1. `[Mie 4:45 pm]` termina el proceso de "compilacion" ya que es un proceso manual que solo funciona en la computadora del desarrollador.
2. `[Mie 5:00 pm]`  __Se pide al equipo de QA \(quality assurance\) que verifique de manera manual el nuevo cambio
3. `[Mie 5:35 pm]` ✅Aceptan el cambio debido a que ese dia "querian" irse temprano
4. `[Jue 9:00 am]` se envia el OK al equipo de liderazgo
5. `[Jue 12:30 pm]` el equipo de liderazgo da el ok via correo electronico, tarda 3.5 hr debido a que se encontraban en una reunion muy importante desde las 9:00 am.
6. `[Jue 2:30 pm]` despues de la hora de almuerzo el equipo de liderazgo vuelve a mandar el correo electronico al equipo de IT/SysAdmin/Ops 
7. \[Jue 4:45 pm

{% hint style="warning" %}
**produccion**: Nadie tiene su ambiente de produccion libre para que alguien haga algun cambio sin los permisos adecuados ¿ verdad? 
{% endhint %}

