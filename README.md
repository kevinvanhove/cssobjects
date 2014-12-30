cssObjects
==========

cssObjects is designed as a new and clear methodology for CSS development. It encompases the naming, structuring and managing of css components. 

cssObjects should be:

- **Independent**:
All objects can be used as stand alone components and can be included in any existing project, even if you are not using the complete methodology

- **Extendable**:
Components can be extended with new functionality without breaking any code

- **Reusable**:
Code should be written with reusability in mind first. Reusable through semantics & pattern design.

Introduction
------------
CSS was originally designed to decorate html, but the vision of css evolved over the years. In later versions, CSS was also used to 'structure' content in addition to decorating it. New ideas like the flexbox show, that the big idea of css still holds, to separate form from function, but that the definition of the term 'form' is now much broader. 

CSS is build on 2 very basic design concepts that are very much at the core of the technology:

1. **the cascading mechanism**
2. **the inheritance of properties**

Like CSS, cssObjects is build on that concept. Every component in cssObjects has been designed to complement the cascading mechanism and the inheritance of properties. 

The layered architecture
------------
It's helpful to view cssObjects as a set of layers. The lowest layer provides the fundamental setup of any project, while the subsequent layers are specialized for the project at hand. Each layer inherits from the layer below.

cssObjects has 4 layers

1. **Document**
2. **Theme**
3. **Structure**
4. **Object**

### 1. Document

The Document layer prepares the browser for the project, it can contain files like:

- **normalize.css**: make browsers render all elements more consistently and in line with modern standards.   
- **global.css**: initialize global variables that can be used project wide.

Document files should normaly not be changed after it has been set up.

### 2. Theme

Every project has a unique look and feel, this look is captured in the 'theme' layer. 

Instead of styling every component individually the theme layer is used to share visual properties. All components hereafter inherit the properties of this layer so that the visual style can remain consistent throughout the entire project. 

The theme layer can include these files:

- **typography**: attachment of @font-face fonts and typographical settings for the project
- **color**: font colors used in the theme
- **background**: setup of background colors, gradients and images

### 3. Structure

The structure is responsible for holding content and objects in some way or form. It responds to the media you are using to view the structure, and it adjusts through the use of media queries. 

There are 3 objects that hold a project's content:

- **layout**
- **grid**
- **model**

#### Layout
Layouts set the parameters of the main wrapper of the project using the ```<main>``` tag. This wrapper can contain the ```<header>```  and ```<footer>``` but also an ```<aside>``` or ```<nav>``` element. All subsequent components and text are positioned inside this wrapper. 

#### Grid
Content can be positioned in a column based grid system. The standard version has 12, percentage based, columns. Depending on the device width, the grid responds and repositions it's columns.

#### Model
A model is like an advanced grid, it's more specific about it's form and isn't as general as the previous structure methods. It can hold any content. Models can be combined to create more complex structure needs, enabling objects to be positioned in any form. Designing clever models makes them reusable.

### 4. Objects

