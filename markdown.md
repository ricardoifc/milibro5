# Archivos de Markdown

Ya sea que escriba el contenido de su libro en Jupyter Notebooks (`.ipynb`) o
en archivos de rebajas regulares (`.md`), escribirá en el mismo tipo de rebajas
llamado ** MyST Markdown **.

## ¿Qué es MyST?

MyST son las siglas de "Texto estructurado marcadamente". Eso
es una ligera variación de un tipo de rebaja denominada rebaja "CommonMark",
con pequeñas extensiones de sintaxis para permitirle escribir ** roles ** y ** directivas **
en el ecosistema de la Esfinge.

## ¿Qué son roles y directivas?

Los roles y las directivas son dos de las herramientas más poderosas de Jupyter Book. Ellos
son funciones similares, pero escritas en un lenguaje de marcado. Ambos
tienen un propósito similar, pero ** los roles están escritos en una línea **, mientras que
** las directivas abarcan muchas líneas **. Ambos aceptan diferentes tipos de entradas,
y lo que hacen con esos insumos depende de la función o directiva específica
que se está llamando.

### Usando una directiva

En su forma más simple, puede insertar una directiva en el contenido de su libro de la siguiente manera:

`` ``
`` `{mydirectivename}
Mi contenido de directiva
''
`` ``

Esto solo funcionará si ya existe una directiva con el nombre `mydirectivename`
(que no es así). Hay muchas directivas predefinidas asociadas con
Libro de Jupyter. Por ejemplo, para insertar un cuadro de nota en su contenido, puede
utilice la siguiente directiva:

`` ``
`` `{nota}
Aquí hay una nota
''
`` ``

Esto resulta en:

`` `{nota}
Aquí hay una nota
''

En tu libro construido.

Para obtener más información sobre la redacción de directivas, consulte la
[Documentación de MyST] ​​(https://myst-parser.readthedocs.io/).


### Usando un rol

Los roles son muy similares a las directivas, pero son menos complejos y están escritos
enteramente en una línea. Puede insertar un rol en el contenido de su libro con
este patrón:

''
Algo de contenido {rolename} `¡y aquí está el contenido de mi función!`
''

Nuevamente, los roles solo funcionarán si "rolename" es un nombre de rol válido. Por ejemplo,
la función `doc` se puede utilizar para hacer referencia a otra página de su libro. Usted puede
referirse directamente a otra página por su ruta relativa. Por ejemplo, el
la sintaxis de rol `` {doc} `intro`` `dará como resultado: {doc}` intro`.

Para obtener más información sobre la redacción de roles, consulte el
[Documentación de MyST] ​​(https://myst-parser.readthedocs.io/).


### Agregar una cita

También puede citar referencias almacenadas en un archivo `bibtex`. Por ejemplo,
la siguiente sintaxis: `` {cite} `holdgraf_evidence_2014`` `se renderizará como
esto: {cite} `holdgraf_evidence_2014`.

Además, puede insertar una bibliografía en su página con esta sintaxis:
La directiva `{bibliography}` debe usarse para todos los roles `{cite}` para
renderizar correctamente.
Por ejemplo, si las referencias de su libro se almacenan en `referencias.bib`,
luego la bibliografía se inserta con:

`` ``
`` `{bibliografía}
''
`` ``

Dando como resultado una bibliografía renderizada que se parece a:

`` `{bibliografía}
''


### Ejecutando código en sus archivos de rebajas

Si desea incluir contenido computacional dentro de estos archivos de rebajas,
puede utilizar MyST Markdown para definir las celdas que se ejecutarán cuando su
se construye el libro. Jupyter Book usa * jupytext * para hacer esto.

Primero, agregue metadatos de Jupytext al archivo. Por ejemplo, para agregar metadatos de Jupytext
a esta página de rebajas, ejecute este comando:

''
jupyter-book myst init markdown.md
''

Una vez que un archivo de rebajas tiene metadatos de Jupytext, puede agregar lo siguiente
directiva para ejecutar el código en el momento de la compilación:

`` ``
`` `{código-celda}
print ("Aquí hay un código para ejecutar")
''
`` ``

Cuando su libro esté construido, el contenido de cualquier bloque `{code-cell}` será
ejecutado con su kernel de Jupyter predeterminado, y sus salidas se mostrarán
en línea con el resto de su contenido.

Para obtener más información sobre la ejecución de contenido computacional con Jupyter Book,
consulte [La documentación de MyST-NB] (https://myst-nb.readthedocs.io/).



Version Ingles

# Markdown Files

Whether you write your book's content in Jupyter Notebooks (`.ipynb`) or
in regular markdown files (`.md`), you'll write in the same flavor of markdown
called **MyST Markdown**.

## What is MyST?

MyST stands for "Markedly Structured Text". It
is a slight variation on a flavor of markdown called "CommonMark" markdown,
with small syntax extensions to allow you to write **roles** and **directives**
in the Sphinx ecosystem.

## What are roles and directives?

Roles and directives are two of the most powerful tools in Jupyter Book. They
are kind of like functions, but written in a markup language. They both
serve a similar purpose, but **roles are written in one line**, whereas
**directives span many lines**. They both accept different kinds of inputs,
and what they do with those inputs depends on the specific role or directive
that is being called.

### Using a directive

At its simplest, you can insert a directive into your book's content like so:

````
```{mydirectivename}
My directive content
```
````

This will only work if a directive with name `mydirectivename` already exists
(which it doesn't). There are many pre-defined directives associated with
Jupyter Book. For example, to insert a note box into your content, you can
use the following directive:

````
```{note}
Here is a note
```
````

This results in:

```{note}
Here is a note
```

In your built book.

For more information on writing directives, see the
[MyST documentation](https://myst-parser.readthedocs.io/).


### Using a role

Roles are very similar to directives, but they are less-complex and written
entirely on one line. You can insert a role into your book's content with
this pattern:

```
Some content {rolename}`and here is my role's content!`
```

Again, roles will only work if `rolename` is a valid role's name. For example,
the `doc` role can be used to refer to another page in your book. You can
refer directly to another page by its relative path. For example, the
role syntax `` {doc}`intro` `` will result in: {doc}`intro`.

For more information on writing roles, see the
[MyST documentation](https://myst-parser.readthedocs.io/).


### Adding a citation

You can also cite references that are stored in a `bibtex` file. For example,
the following syntax: `` {cite}`holdgraf_evidence_2014` `` will render like
this: {cite}`holdgraf_evidence_2014`.

Moreoever, you can insert a bibliography into your page with this syntax:
The `{bibliography}` directive must be used for all the `{cite}` roles to
render properly.
For example, if the references for your book are stored in `references.bib`,
then the bibliography is inserted with:

````
```{bibliography}
```
````

Resulting in a rendered bibliography that looks like:

```{bibliography}
```


### Executing code in your markdown files

If you'd like to include computational content inside these markdown files,
you can use MyST Markdown to define cells that will be executed when your
book is built. Jupyter Book uses *jupytext* to do this.

First, add Jupytext metadata to the file. For example, to add Jupytext metadata
to this markdown page, run this command:

```
jupyter-book myst init markdown.md
```

Once a markdown file has Jupytext metadata in it, you can add the following
directive to run the code at build time:

````
```{code-cell}
print("Here is some code to execute")
```
````

When your book is built, the contents of any `{code-cell}` blocks will be
executed with your default Jupyter kernel, and their outputs will be displayed
in-line with the rest of your content.

For more information about executing computational content with Jupyter Book,
see [The MyST-NB documentation](https://myst-nb.readthedocs.io/).
