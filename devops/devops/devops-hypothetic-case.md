---
description: >-
  Realizaremos un ejercicio hipotetico a lo largo de todo este material para que
  usted observe la importancia de cada uno de los pilares y componentes de
  Devops.
---

# Devops - Hypothetic Case

💡**Supongamos el siguiente caso hipotetico:**

Usted es encargado de una pagina web donde se venden algunos productos, millones de usuarios lo visitan al dia. 

{% hint style="danger" %}
Reportan que en la pagina de inicio hay un error de escritura \(como el de la imagen de abajo\)
{% endhint %}

![](../../.gitbook/assets/screen-shot-2020-03-10-at-8.28.44-pm.png)



**¿ Cuánto tiempo le tomaria a su equipo, con los procesos actuales, arreglar este error ?**

{% hint style="info" %}
Segun [DORA](https://devops.com/the-state-of-devops-report-2019-is-out/) \(DevOps Research and Assessment\) las empresas en general les tomaria:

* El 20% entre **1 hora a 1 dia**
* El 23% entre **1 semana a 1 dia**
* El 44% entre **1 semana a 1 mes**
* El 12% entre **1 mes a 6 meses**

> ¿ ****a que grupo perteneceria su empresa?
{% endhint %}

## **Code**

Este es el código fuente de su página web.  ****

```text
#index.html
<h1>
Mi página de Productos:
</h1>

<ul>
<li> <h2> Producto 1 </h2></li>
<li> <h2> Producto 2 </h2></li>
<li> <h2> Producto 3 </h2></li>
<li> <h2> Producto 4 </h2></li>
 
<li> <h2> Producto cun eror </h2></li>
</ul>
```

> Nada fuera de lo normal verdad?

