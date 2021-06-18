# Desencripta API 

## Aplicación
La aplicación consiste en crear un API RESTful que sirva para desencriptar mensajes.
El API debe contar con los siguientes recursos:
* `freqlang`: Tabla de frecuencias.
* `decrypt`: Método para desencriptar mensajes. 

Si se sabe que solo se han encriptado los caracteres del alfabeto inglés (a - z).
El método `decrypt` deberá ordenar las letras del mensaje encriptado de acuerdo al número de veces que se repiten (de mayor a menor) y compararlo con la tabla de frecuencia de caracteres del lenguaje en que está escrito este mensaje.


Con ayuda del ORM crear el modelo `FrequencyTable` con los siguientes campos:
* `pk`: Int 
* `freqlang`: String 
* `created`: Datetime (Read Only). Seteado al crearse un nuevo record.

Ejemplo:
```
freqlang = "TEOIARNSHLMYUCWDGPFBVKJ"  # De más frecuente a menos frecuente. (Da igual mayúsculas o minúsculas).
```


## Requerimientos 
* Usar el framework [FastApi](https://fastapi.tiangolo.com/)
* Usar [Tortoise ORM](https://tortoise-orm.readthedocs.io/en/latest/)
* Usar Postgres.
* Usar Docker y Docker Compose. 


## Tareas 

* Implementar el un CRUD con el recurso `freqlang`. Se deben soportar los siguientes métodos:
  * POST: `/freqlang` -> Inputs: `freqlang`
  * PUT: `/freqlang` -> Inputs: `pk`
  * GET: `/freqlang/{pk}`
  * GET: `/freqlang` -> De todos los records.
  * DELETE: `/freqlang/{pk}` -> Inputs: `pk` 
* Implementar el endpoint `/freqlang/decrypt` que reciba el payload `message` (via POST) y usando el último record de `FrequencyTable` retorne el `message` desencriptado. 
* Implementar el endpoint `/freqlang/{pk}/decrypt` que reciba el payload `message` (via POST) y usando el record `pk` del `FrequencyTable`retorne el `message` desencriptado. 
* Generar y publicar la imágen generada en [Docker Hub](https://hub.docker.com/)
* El proyecto debe tener las intrucciones para levantar la imagen de forma local: README.md
* Compartir por email el proyecto de github.
* Dentro de `SOLUTION.txt`, guardar el mensaje desencriptado con los siguientes inputs:

```
{
  "freqlang": "TEOIARNSHLMYUCWDGPFBVKJ"
}
```

Mensaje:
```
uid nx, aex jcdjipx iu wzux zp, ta wxtpa jtdaws, ai etkx vis.
dcos zyexdzaxr aex jxdw jezwipijes iu etkzyg nidx aety iyx hts
ai ri aex ptnx aezyg. z zyexdzaxr aeta jezwipijes udin wtdds htww,
hei zp ns exdi tqactwws. z htya ai ntfx dcos cpxdp udxx. z htya ai
gzkx aexn aex udxxrin ai qeiipx. jxijwx tdx rzuuxdxya. jxijwx qeiipx
rzuuxdxya qdzaxdzt. oca zu aexdx zp t oxaaxd hts tniyg ntys
twaxdytazkxp, z htya ai xyqicdtgx aeta hts os ntfzyg za qinuidatowx.
pi aeta'p heta z'kx adzxr ai ri.
z htya ai piwkx jdiowxnp z nxxa zy aex rtzws wzux os cpzyg qinjcaxdp,
pi z yxxr ai hdzax jdigdtnp. os cpzyg dcos, z htya ai qiyqxyadtax aex
aezygp z ri, yia aex ntgzqtw dcwxp iu aex wtygctgx, wzfx patdazyg hzae
jcowzq kizr  pinxaezyg pinxaezyg pinxaezyg ai pts, "jdzya exwwi hidwr."
z vcpa htya ai pts, "jdzya aezp!" z riy'a htya tww aex pcddicyrzyg
ntgzq fxshidrp. z vcpa htya ai qiyqxyadtax iy aex atpf. aeta'p aex otpzq
zrxt. pi z etkx adzxr ai ntfx dcos qirx qiyqzpx tyr pcqqzyqa.
scfzezdi ntapcniai. (hhh.tdaznt.qin/zyak/dcos)
```
