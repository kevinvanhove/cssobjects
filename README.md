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

An object (like a simple button) is a stand-alone collection of CSS code that inherits the properties of the lower layers. They are organized by **topic(T)**, **subject(S)** and **class(C)**. We will refer to this method as the **TSC standard**. 

There are 4 topics(T), they differ in the way they communicate with the user:

- **Presentation** boxes to captivate the user
- **State** objects to inform the user
- **UI controls** to interact with the user
- **Navigation** elements to guide the user

Each of the 4 topics(T) can have several subjects(S):

**Presentation**
- list
- article
- box
- figure
- gallery
- head
- header
- quote
- table


**State**
- badge
- tag	
- progress

**UI**
- button
- form
- link
- tab
- toolbar

**Navigation**
- index
- nav

Finally each subject(S) has 1 or more classes(C), they form the actual object that can be used in a HTML project .

**UI**
- button.css
  - .button
  - .buttonGroup
  - .buttonBlock
  - .buttonForm

Creating an object
------------
For quality control to work we need a system that is standard and universal. We have to adopt conventions in every step of the development process. 

cssObjects adopts a code writing style based on hierarchy that can be used for every object in a project. It's very visual in that a developer can easily see the construction of an object, distinguish it's parts and view any versions of the object.

### Construction

An object has 4 sections:

- **Class**: The main component name, for instance .tablePricing
- **Part**: Named elements or 'parts' inside an object, for instance . tablePricing-heading
- **Version**: Other versions of the object, for instance . tablePricing.small
- **Media**: Classes, parts or versions that change using media queries


| Section        | Convention           |
| ------------- |-------------|
| Class      | .className |
| Part      | .className-part      |
| Version | .className.version      |

### Pattern

To differentiate between the 4 sections we use a combination of css comments, white space and hierarchy. This pattern design also helps to evaluate the concept of css specificity.

At it's base the pattern goes like this:

``` css
.class
.class li

.class-part

.class.version
.class.version li

.class.version .class-part

.media
```

If an object is more bulky, has more parts or versions then we use css commenting to keep the 4 sections organized.

Naming convention
------------
Many developers have trouble selecting class names for their components. There is also the consideration that a class name should be semantic in it's nature. To streamline this process cssObjects uses the TSC standard to help define the right class name for each object.

Ask yourself these question in relation to the TSC standard:

- Of what **topic(T)** is the object
- To what **subject(S)** can it belong
- What function does the **class(C)** have?

To establish the name we combine the subject(S) with it's class(C) function. The words are combined using camelCase, where the first letter of the subject(S) is lowercase and the first letter of each subsequent concatenated class(C) name is capitalized. 

### Example 1

What we need: a box to style a commercial square banner

```
Topic(T)
- presentation

Subject(S)
- box

Class(C)
- square banner
```

CSS: **.boxSquareBanner** in file: **box.css**

### Example 2

What we need: a list of text links with check icons aligned to the left

```
Topic(T)
- presentation

Subject(S)
- list

Class(C)
- check icon
```

CSS: **.listCheckIcon** in file: **list.css**

### Example 3

What we need: a full screen kind of button to continue to the next page

```
Topic(T)
- user interface

Subject(S)
- button

Class(C)
- continue to page
```

CSS: **.buttonContinueToPage** in file: **button.css**

A collection of TSC names
------------
- ui
- interface
- image
- illustration
- logo
- icon
- script
- sign
- link
- type
- deck
- news
- photo
- badge
- dock
- blur
- animation
- set
- symbol
- menu
- page
- landing
- date
- price
- quote
- player
- widget
- movie
- cycle
- album
- brand
- process
- char
- table
- pattern
- box
- post
- text
- client
- chat
- marker
- poster
- frame
- panel
- music
- sketch
- radio
- line
- comment
- profile
- setting
- nav
- form
- status
- dashboard
- button
- aside
- article
- toolbar
- window
- data
- tab
- bar
- layout
- tag
- calendar
- note
- task
- header
- thumb
- flag
- map
- slider
- ticket
- chart
- loading
- picker
- focus
- admin
- app
- switch



