# CD - Hypothetic Case

Tomemos el mismo caso [expuesto en CI](../continuous-integration/ci-hypothetic-case.md).

{% tabs %}
{% tab title="Source Code" %}
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
{% endtab %}

{% tab title="WebServer Configuration Change" %}
```text
if ($request_method = 'POST') {
        add_header 'Access-Control-Allow-Origin' '*';
        add_header 'Access-Control-Allow-Methods' 'GET, POST, OPTIONS';
        add_header 'Access-Control-Allow-Headers' 'DNT,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Range';
        add_header 'Access-Control-Expose-Headers' 'Content-Length,Content-Range';
}
```
{% endtab %}
{% endtabs %}

> Note que el cambio ahora incluye una mejora a la configuracion del WebServer para que sea efectivo TODO la integracion

1. `[Mie 4:45 pm]` termina el proceso de "compilacion" ya que es un proceso manual que solo funciona en la computadora del desarrollador.
2. `[Mie 5:00 pm]`  __Se pide al equipo de QA \(quality assurance\) que verifique de manera manual el nuevo cambio
3. `[Mie 5:35 pm]` ✅Aceptan el cambio debido a que ese dia "querian" irse temprano
4. `[Jue 9:00 am]` se envia el OK al equipo de liderazgo
5. `[Jue 12:30 pm]` el equipo de liderazgo da el ok via correo electronico, tarda 3.5 hr debido a que se encontraban en una reunion muy importante desde las 9:00 am.
6. `[Jue 2:30 pm]` despues de la hora de almuerzo el equipo de liderazgo vuelve a mandar el correo electronico al equipo de IT/SysAdmin/Ops 
7. `[Jue 4:45 pm]` el equipo de IT tarda 2 horas con 15 minutos debido a que se encontraban arreglando otro problema con lo\(s\) servidor\(es\) de produccion.
8. **`[Jue 4:55 pm]` el equipo de IT pide via correo el zip con el contenido de los cambios**
9. **`[Jue 5:00 pm ]` el equipo de desarrollo envia los cambios a aplicar dentro de un zip \(pero olvida enviar una configuracion adicional para el WebServer, IIS, Nginx, Apache, etc\)**
10. **`[Jue 5:10 pm]` el equipo de IT confiadamente aplica los cambios enviados por el equipo de desarrollo, sin percatarse que hacia falta un cambio que se debia aplicar manualmente al WebServer, ocasionando una interrupcion al servicio, nadie se percata de esta disrupcion.**
11. **`[Jue 5:30 pm]` los clientes llaman molestos debido que el servicio se encuentra interrumpido, el equipo de IT inmediatamente contacta con el equipo de desarrollo**
12. **`[Jue 5:40 pm]` el \(los\) desarrollador debe volver del trafico a su lugar de trabajo para intentar resolver el problema** 
13. **`[Jue 6:40 pm]` se toma ~1 hora hasta percatarse que no se envio en el correo ni en el zip el cambio al WebServer, ahora se vuelve a enviar el archivo zip pero con ambos cambios**
14. **`[Jue 6:50 pm]` el equipo de IT ahora desconfiadamente aplica los cambios esperando que esto arregle el problema**
15. **`[Jue 7:00 pm]` el servicio es restablecido**
16. **`[Vie | Sab | Dom]` el servicio pasa funcionando 24 horas pero con un pequeño problema.**
17. `[Lun 9:00 am]` se percatan que el cambio que se introdujo **el desarrollador** tenia problemas y que no corrigio el problema por completo \(le hace falta una `r` en la palabra `eror` \)por lo tanto se repite exactamente el mismo proceso.

Tomemos algunas lecciones de este caso hipotetico:

* Todo el tiempo muerto entre la comunicacion de equipo a equipo.
*  El servicio paso ~ 2 horas \(en el mejor de los casos\) interrumpido.
* El tiempo de recuperacion fue de ~2 horas.
* El tiempo para poder hacer un Release fue tardado porque todo fue manual, los cambios al WebServer no fueron de ninguna manera automatizados.
* El tiempo para volver a hacer un Release fue de ~6 dias \(+ el tiempo en hacer el cambio de la  `r`, aproximadamente otros 5 dias? \)



{% hint style="info" %}
Cualquier parecido con la realidad es pura coincidencia
{% endhint %}

