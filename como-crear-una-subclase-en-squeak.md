Para crear una subclase hay dos formas:

Forma A
-------

1. En un class browser ctrl-click sobre la superclase, les abre un menú contextual. Ahí "more..." y luego "subclass template". 2. Les va a aparecer un texto parecido a este (en mi ejemplo tomé como superclase a la clase Ave):

`Ave subclass: #NameOfSubclass`
`    instanceVariableNames: ''`
`    classVariableNames: ''`
`    poolDictionaries: ''`
`    category: 'PDEP-EjemploGolondrinas'`

3. Reemplazar "\#NameOfSubclass" por el nombre de la clase que quieran (ojo hay que dejar el "\#") 4. Pueden agregar variables de instancia y de clase (entre comillas simples y separadas por espacios). 5. Elegir la categoría que queran, por defecto les va a aparecer la misma categoría que la superclase (les conviene poner todas sus clases en una categoría propia (o un varias categorías propias si quieren diferenciarlas de alguna manera). Si ponen un nombre de categoría nuevo les va a crear la categoría junto con la clase. 6. Salvar (ctrl+s o ctrl+click, accept... (\*))

Si ven bien los pasos 3-5 son para cualquier clase, la gran diferencia es que para crear una clase común dice "Object" en lugar de "Ave" (es decir, todas nuestras clases son subclases de Object, salvo que yo le indique alguna otra más específica).

Forma B
-------

Una forma que puede resultar más sencilla es directamente copiar el texto que está arriba en la sección de código del Class Browser (eso reemplaza los puntos 1 y 2) y luego modificarlo y salvarlo (igual a los pasos 3-6).

(Asegúrense de borrar todo lo que haya en la sección de código antes, es decir, tiene que ser el único texto en ese lugar, lo modifican y lo graban, voilá).