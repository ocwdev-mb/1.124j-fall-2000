---
content_type: page
description: ''
learning_resource_types:
- Lecture Notes
ocw_type: CourseSection
parent_title: Lecture Notes
parent_type: CourseSection
parent_uid: dd846b6b-f0c7-fd62-35a9-4e87d772d0e9
title: Java 3D Lecture
uid: c9c9104a-ac54-a054-d006-354e424ccb63
video_files:
  video_thumbnail_file: null
video_metadata:
  youtube_id: null
---

This lecture is courtesy of Petros Komodromos.
----------------------------------------------

Topics
------

1.  [Introduction to Java® 3D](#1)
2.  [Java® 3D References](#2)
3.  [Examples and Applications](#3)
4.  [Scene Graph Structure and basic Java® 3D concepts and classes](#4)
5.  [A simple Java® 3D program](#5)
6.  [Performance of Java® 3D](#6)

{{< anchor "1" >}}{{< /anchor >}}1\. Introduction to Java® 3D
-------------------------------------------------------------

_Java® 3D_ is a general-purpose, platform-independent, object-oriented API for 3D-graphics that enables high-level development of Java® applications and applets with 3D interactive rendering capabilities. With _Java® 3D_, 3D scenes can be built programmatically, or, alternatively, 3D content can be loaded from VRML or other external files. _Java® 3D_, as a part of the _Java® Media APIs_, integrates well with the other [Java® technologies and APIs](http://java.sun.com/products/). For example, [_Java® 2D_](http://java.sun.com/products/java-media/2D/index.html) API can be used to plot selected results, while the [_Java® Media Framework (JMF)_](http://java.sun.com/products/java-media/jmf/index.html) API can be used to capture and stream audio and video.

Java® 3D is based on a directed acyclic graph-based scene structure, known as scene graph, that is used for representing and rendering the scene. The scene structure is a tree-like diagram that contains nodes with all the necessary information to create and render the scene. In particular, the [scene graph](#4) contains the nodes that are used to represent and transform all objects in the scene, and all viewing control parameters, i.e. all objects with information related to the viewing of the scene. The scene graph can be manipulated very easily and quickly allowing efficient rendering by following a certain optimal order and bypassing hidden parts of objects in the scene.

Java® 3D API has been developed under a joint collaboration between Intel, Silicon Graphics, Apple, and Sun, combining the related knowledge of these companies. It has been designed to be a platform-independent API concerning the host's operating system (PC/Solaris/Irix/HPUX/Linux) and graphics (OpenGL/Direct3D) platform, as well as the input and output (display) devices. The implementation of Java® 3D is built on top of OpenGL, or Direct3D. The high level Java® 3D API allows rapid application development which is very critical, especially nowadays.

However, Java® 3D has some weaknesses such as the performance, which is inferior to that of OpenGL, and the limited access to the rendering pipeline details. It is also still under development and several bugs need to be fixed. Although Java® 3D cannot achieve peak performance, portability and rapid development advantages may overweigh the slight performance penalty for many applications.

The current version of the Java® 3D API is the Version 1.2, which works together with the [Java® 2 Platform](http://java.sun.com/j2se/). Both APIs can be downloaded for free from the [Java® products page of Sun](http://java.sun.com/products/).  
  
  
 

{{< anchor "2" >}}{{< /anchor >}}2\. Java® 3D References
--------------------------------------------------------

The following list includes many links related to the Java® 3D API

*   [_Java® 3D 1.2 API Documentation_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/index.html)  [](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/index.html) 
*   [_Java® 3D 1.2 Specification_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dguide/index.html)  
*   Java® 3D Tutorial (PDF format):
    *   [_Chapter 0_](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch0.pdf) [](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch0.pdf) , Preface, Appendices, and Glossary
    *   [_Chapter 1_](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch1.pdf) , Getting Started
    *   [_Chapter 2_](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch2.pdf) , Creating Content
    *   [_Chapter 3_](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch3.pdf) , Easier Content Creation
    *   [_Chapter 4_](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch4.pdf) [](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch4.pdf) , Interaction
    *   [_Chapter 5_](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch5.pdf) [](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch5.pdf) , Animation
    *   _[Chapter 6](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch6.pdf) [](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch6.pdf) _ , Lights
    *   [_Chapter 7_](http://java.sun.com/products/java-media/3D/collateral/j3d_tutorial_ch7.pdf) , Textures  
         
*   _[3D Graphics Programming with Java® 3D](http://www.javaworld.com/article/2076832/java-se/3d-graphics-programming-in-java--part-1--java-3d.html)_ (very informative - PDF format)
*   [_Raw J3D_](http://www.java3d.org/)
*   [_Java® 3D: For Developers and End-Users_](http://java.sun.com/developer/Books/Java3D/)
*   _A Fourth generation Java® 3D graphics API_[](http://www.javaworld.com/javaworld/jw-12-1998/jw-12-media.html)
*   [_Java® 3D Datasheet_](http://www.oracle.com/technetwork/java/javase/tech/index-jsp-138252.html)
*   [_White paper: The Java® 3D API_](https://www.oracle.com/java/technologies/javase/javase-whitepapers.html)  (technical paper)
*   _Java® 3D FAQ at Sun_
*   [_Java® 3D Community FAQ_](http://www.j3d.org/contact.html)
*   _Extensive Java® 3D FAQ at Sun_
*   _Java® 3D Group at NCSA_
*   [_Java® 3D Community site_](http://www.j3d.org/)
*   _The Java® 3D and VRML Working group_
*   _VRML and Java® 3D Information Center_
*   _Web 3D consortium_
*   [_Java® 3D Loader Archive_](http://www.mail-archive.com/java3d-interest@java.sun.com/)

Java® 3D is specified in the packages: [_javax.media.j3d_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/package-summary.html) and [_javax.vecmath_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/vecmath/package-summary.html). Supporting classes and utilities are provided in the _com.sun.j3d_ packages.

{{< anchor "3" >}}{{< /anchor >}}3\. Examples and Applications
--------------------------------------------------------------

The following are examples provided by Java® 3D in directories with the names as follows under the subdirectory _java3d_ of the directory _demo_.

*   AlternateAppearance
*   Appearance
*   AppearanceMixed
*   AWT\_Interaction: _java AWTInteraction_
*   Background
*   Billboard
*   ConicWorld: _java  SimpleCylinder_ ; _java  TexturedSphere_
*   FourByFour: _appletviewer fbf.html_
*   GearTest: _java GearBox_
*   GeometryByReference
*   GeometryCompression
*   HelloUniverse
*   Lightwave
*   LOD
*   ModelClip
*   Morphing
*   ObjLoad
*   OffScreenCanvas3D
*   OrientedShape3D
*   PackageInfo
*   PickTest
*   PickText3D: _java PickText3DGeometry_
*   PlatformGeometry
*   PureImmediate
*   ReadRaster
*   Sound
*   SphereMotion: _appletviewer SphereMotion.html_
*   SplineAnim
*   Text2D
*   Text3D
*   TextureByReference
*   TextureTest
*   TickTockCollision:  _java TickTockCollision_
*   TickTockPicking
*   VirtualInputDevice

For example, on a Sun Ultra 10 workstation the files for the _GearTest_ example are located under the subdirectory:_  
  
mit/java\_v1.2ref/distrib/sun4x\_56/demo/java3d/GearTest_

Similarly, if you download _Java® 3D_ on your computer, the examples are typically stored in subdirectories in the subdirectory _demo\\java3d_ of the directory where Java® has been downloaded, e.g. at _C:\\Java\\jdk1.3\\demo\\java3d_.

There are many fields in which Java® 3D can be used. The following are just a small selection of Java® 3D applications that are available on the net.

*   _NCSA Astro3D_
*   [_Collaborative Visualization Space Science and Engineering Center (SSEC)_](http://www.ssec.wisc.edu/~billh/visad.html#immersion)
*   [_Java® 3D API Customer Success Stories_](http://java.sun.com/products/java-media/3D/in_action/)

{{< anchor "4" >}}{{< /anchor >}}4\. Scene Graph Structure and Basic Java® 3D Concepts and Classes
--------------------------------------------------------------------------------------------------

_Scene graph: Content-View Branches_

A Java® 3D scene is created as a tree-like graph structure, which is traversed during rendering. The scene graph structure contains nodes that represent either the actual objects of the scene, or, specifications that describe how to view the objects. Usually, there are two  branches in Java® 3D, the **content branch**, which contains the nodes that describe the actual objects in the scene, and  the **view branch**, which contains nodes that specify viewing related conditions. Usually, the content branch contains much larger number of nodes than the view branch.

The following image shows a basic Java® 3D graph scene, where the content branch is located on the left and the view branch on the right side of the graph:

{{< resource "cb6b58f7-abe0-910f-9d4c-1a4e758995c5" >}}

Java® 3D applications construct individual graphic components as separate objects, called nodes, and connects them together into a tree-like scene graph, in which the objects and the viewing of them can easily be manipulated. The scene graph structure contains the description of the virtual universe, which represents the entire scene. All information concerning geometric objects, their attributes, position and orientation, as well as the viewing information are all contained into the scene graph.

The above scene graph consists of superstructure components, in particular a [_VirtualUniverse_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/VirtualUniverse.html) and a [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html) object, and a two [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) objects, which are attached to the superstructure. The one branch graph, rooted at the left [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) node, is a content branch, containing all the relevant to the contents of the scene objects. The other branch, known as view branch, contains all the information related to the viewing and the rendering details of the scene.

The state of a shape node, or any other leaf node, is defined, during rendering, by the nodes that lie in the direct path between that node and the root node, i.e. the [_VirtualUniverse_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/VirtualUniverse.html). For example, a [_TransformGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransformGroup.html) node in a path between a leaf node and the scene's root can change the position, orientation, and scale of the object represented by the leaf node.

[_SceneGraphObject_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/SceneGraphObject.html) Hierarchy
-------------------------------------------------------------------------------------------------------------------------------------

The Java® 3D node objects of a Java® 3D scene graph, which are instances of the [_Node_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Node.html) class, may reference node component objects, which are instances of the class NodeComponent. The [_Node_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Node.html) and [_NodeComponent_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/NodeComponent.html) classes are subclasses of the [_SceneGraphObject_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/SceneGraphObject.html) abstract class. Almost all objects that may be included in a scene graph are instances of subclasses of the [_SceneGraphObject_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/SceneGraphObject.html) class. A scene graph object is constructed by instantiating the corresponding class, and then, it can be accessed and manipulated using the provided set and get methods.

The following graph shows the class hierarchy of the major subclasses of the [_SceneGraphObject_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/SceneGraphObject.html) class:

{{< resource "d718435c-535c-ef73-9917-b89c8413f90f" >}}

_Class [Node](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Node.html)_ _and its subclasses_

The abstract Class [_Node_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Node.html) is the base class for almost all objects that constitute the scene graph. It has two subclasses the [_Group_,](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Group.html) and [_Leaf_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/Leaf.html) classes, which have many useful subclasses. Class [_Group_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/Group.html) is a superclass of, among others, the classes [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) and [_TransformGroup_.](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransformGroup.html) Class [_Leaf_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/Leaf.html), which is used for nodes with no children, is a superclass of, among others, the classes [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html), [_Light_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Light.html), [_Shape3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Shape3D.html), and [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/ViewPlatform.html). The [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) node is used to define from where the scene is viewed. In particular, it can be used to specify the location and the orientation of the point of view.

_Class_ [_NodeComponent_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/NodeComponent.html) _and its subclasses_

Class [_NodeComponent_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/NodeComponent.html) is the base class for classes that represent attributes associated with the nodes of the scene graph. It is the superclass of all scene graph node component classes, such as the [_Appearance_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Appearance.html), [_Geometry_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Geometry.html), [_PointAttributes_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/PointAttributes.html), and [_PolygonAttributes_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/PolygonAttributes.html) classes. [_NodeComponent_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/NodeComponent.html) objects are used to specify attributes for a node, such as the color and geometry of a shape node, i.e. a [_Shape3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Shape3D.html) node. In particular, a [_Shape3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Shape3D.html) node uses an [_Appearance_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Appearance.html) and a [_Geometry_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Geometry.html) objects, where the [_Appearance_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Appearance.html) object is used to control how the associated geometry should be rendered by Java® 3D.

The geometry component information of a [_Shape3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Shape3D.html) node, i.e. its geometry and topology, can be specified in an instance of a subclass of the abstract [_Geometry_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Geometry.html) class. A Geometry object is used as a component object of a [_Shape3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Shape3D.html) leaf node. Geometry objects consist of the following four generic geometric types. Each of these geometric types defines a visible object, or a set of objects.

*   [_CompressedGeometry_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/CompressedGeometry.html)
    
*   [_GeometryArray_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html)
*   [_Raster_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Raster.html)
    
*   [_Text3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Text3D.html)

For example, the [_GeometryArray_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html) is a subclass of the class [_Geometry_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Geometry.html), which itself extends the [_NodeComponent_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/NodeComponent.html) class, that is extended to create the various primitive types such as lines, triangle strips and quadrilaterals.

{{< resource "d404ba55-8789-1a59-f627-8f8ae65b49b3" >}}

The [_IndexedGeometryArray_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/IndexedGeometryArray.html) object above contains separate integer arrays that index, among others, into arrays of positional coordinates specifying how vertices are connected to form geometry primitives. This class is extended to create the various indexed primitive types, such as [_IndexedLineArray_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/IndexedLineArray.html), [_IndexedPointArray_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/IndexedPointArray.html), and [_IndexedQuadArray_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/IndexedQuadArray.html).

Vertex data may be passed to the geometry array either by copying the data into the array using the existing methods, which is the default mode, or by passing a reference to the data.

The methods for setting positional coordinates, colors, normals, and texture coordinates, such as the method [_setCoordinates_()](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html#setCoordinates_int__javax_vecmath_Point3d___), copy the data into the [_GeometryArray_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html), which offers much flexibility in organizing the data.

Another set of methods allows data to be passed and accessed by reference, such as the [_setCoordRef3d_()](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html#setCoordRef3d_javax_vecmath_Point3d___) method, set a reference to user-supplied data, e.g. coordinate arrays. In order to enable the passing of data by reference, the [_BY_\__REFERENCE_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html#BY_REFERENCE) bit in the [_vertexFormat_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html#GeometryArray_int__int_) field of the constructor for the corresponding [_GeometryArray_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html) must be set accordingly. Data in any array that is referenced by a live or compiled [_GeometryArray_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html) object may only be modified using the [_updateData_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html#updateData_javax_media_j3d_GeometryUpdater_) method assuming that the [_ALLOW\_REF\_DATA\_WRITE_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/GeometryArray.html#ALLOW_REF_DATA_WRITE) capability bit is set accordingly, which can be done using the [_setCapability_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/SceneGraphObject.html#setCapability_int_) method.

The [_Appearance_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Appearance.html) object defines all rendering state that control the way the associated geometry should be rendered. The rendering state consists of the following:

*   Point attributes: a [_PointAttributes_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/PointAttributes.html) object defines attributes used to define points, such as the size to be used
*   Line attributes: using a [_LineAttributes_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/LineAttributes.html) object attributes used to define lines, such as the width and pattern, can be defined
*   Polygon attributes: using a [_PolygonAttributes_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/PolygonAttributes.html) object the attributes used to define polygons, such as rasterization mode (i.e.. filled, lines, or points) are defined
*   Coloring attributes: a [_ColoringAttributes_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ColoringAttributes.html) object is used to defines attributes used in color selection and shading.
*   Rendering attributes: defines rendering operations, such as whether invisible objects are rendered, using a [_RenderingAttributes_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/RenderingAttributes.html) object.
*   Transparency attributes: a [_TransparencyAttributes_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransparencyAttributes.html) defines the attributes that affect transparency of the object
*   Material: a [_Material_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Material.html) object defines the appearance of an object under illumination, such as the ambient color, specular color, diffuse color, emissive color, and shininess. It is used to control the color of the shape.
*   Texture: the texture image and filtering parameters used, when texture mapping is enabled, can be defined in a [_Texture_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Texture.html) object.
*   Texture attributes: a [_TextureAttributes_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TextureAttributes.html) object can be used to define the attributes that apply to texture mapping, such as the texture mode, texture transform, blend color, and perspective correction mode.
*   Texture coordinate generation: the attributes that apply to texture coordinate generation can be defined in a [_TexCoordGeneration_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TexCoordGeneration.html) object.
*   Texture unit state: array that defines texture state for each of N separate texture units allowing multiple textures to be applied to geometry. Each [_TextureUnitState_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TextureUnitState.html) object contains a Texture object, TextureAttributes, and TexCoordGeneration object for one texture unit.

**[_VirtualUniverse_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/VirtualUniverse.html)**

and [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html)
-----------------------------------------------------------------------------------------------------------------------

After constructing a subgraph, it can be attached to a [_VirtualUniverse_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/VirtualUniverse.html) object through a high-resolution [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html) object, which is itself attached to the virtual universe. The [_VirtualUniverse_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/VirtualUniverse.html) is the root of all Java® 3D scenes, while [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html) objects are used for basic spatial placement. The attachment to a [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html) object makes all objects in the attached subgraph live (i.e. drawable), while removing it from the locale reverses the effect. Any node added to a live scene graph becomes live. However, in order to be able to modify a live node the corresponding [_capability_ bits](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/SceneGraphObject.html#setCapability_int_) should be set accordingly.

Typically, a Java® 3D program has only one [_VirtualUniverse_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/VirtualUniverse.html) which consists of one, or more, [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html) objects that may contain collections of subgraphs of the scene graph that are rooted by [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) nodes, i.e. a large number of  branch graphs. Although a [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html) has no explicit children, it may reference an arbitrary number of [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) nodes. The subgraphs contain all the scene graph nodes that exist in the universe. A [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/Locale.html) node is used to accurately position a branch graph in a universe specifying a location within the virtual universe using high-resolution coordinates ([_HiResCoord_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/HiResCoord.html)), which represent 768 bits of floating point values. A [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html) is positioned in a single [_VirtualUniverse_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/VirtualUniverse.html) node using one of its constructors.

The [_VirtualUniverse_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/VirtualUniverse.html) and [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html) classes, as well as the [_View_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html) class, are subclasses of the basic superclass [_**Object**_](https://docs.oracle.com/javase/tutorial/java/IandI/objectclass.html), as shown below:

{{< resource "e45316c9-a420-f0b0-66d3-544026497bcd" >}}  
  
 

Branch Graphs
-------------

A branch graph is a scene graph rooted in a [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) node and can be used to point to the root of a scene graph branch. A graph branch can be added to the list of branch graphs of a [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html) node using its [_addBranchGraph_(_BranchGroup_ bg)](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html#addBranchGraph_javax_media_j3d_BranchGroup_) method. [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) objects are the only objects that can be inserted into a [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html)_'s_ list of objects.

A [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) may be compiled by calling its compile method, which causes the entire subgraph to be compiled including any [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) nodes that may be contained within the subgraph. A graph branch, rooted by a  [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) _node,_ becomes live when inserted into a virtual universe by attaching it to a [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html). However, if a [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) is contained in another subgraph as a child of some other group node, it may not be attached to a [_Locale_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Locale.html) node.

Capability Bits, Making Live and Compiling

Certain optimizations can be done to achieve better performance by compiling a subgraph into an optimized internal format, prior to its attachment to a virtual universe. However, many _set_ and _get_ methods of objects that are part of a live or compiled scene graph cannot be accessed. In general, the _set_ and _get_ methods can be used only during the creation of a scene graph, except where explicitly allowed, in order to allow certain optimizations during rendering. The set and get methods that can be used when the object is live or compiled should be specified using a set of capability bits, which by default are disabled, prior to compiling or making live the object. The methods [_isCompiled()_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/SceneGraphObject.html#isCompiled__) and [_isLive()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/SceneGraphObject.html#isLive__) can be used to find out whether a scene graph object is compiled or live. The methods [_setCapability_()](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/SceneGraphObject.html#setCapability_int_) and [_getCapability_()](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/SceneGraphObject.html#getCapability_int_) can be used to set properly the capability bits to allow access to the object's methods. However, the less the capability bits that are enabled, the more optimizations can be performed during rendering.

Viewing Branch: [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html)_, _ [_View_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html)_,_ [_Screen3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Screen3D.html)

The view branch has usually the following structure, consisting of nodes that control the viewing of the scene.

{{< resource "be7231df-1539-a99c-6e1a-611c255912f1" >}}

The view branch contains some scene graph viewing objects that can be used to define the viewing parameters and details, such as the [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html), [_View_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html), [_Screen3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Screen3D.html), [_PhysicalBody_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/PhysicalBody.html), and [_PhysicalEnvironment_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/PhysicalEnvironment.html) classes.

Java® 3D uses a viewing model that can be used to transform the position and direction of the viewing while the content branch remains unmodified. This is achieved with the use of the [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) and the [_View_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html) classes, to specify from where and how, respectively, the scene is being viewed.

The [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) node controls the position, orientation and scale of the viewer. A viewer can navigate through the virtual universe by changing the transformation in the scene graph hierarchy above the [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) node. The location of the viewer can be set using a [_TransformGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransformGroup.html) node above the [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) node. The [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) node has an activation radius that is used together with the bounding volumes of [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html), [_Background_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Background.html) and other nodes in order to determine whether the latter nodes should be scheduled, or turned on, respectively. The method [_setActivationRadius_()](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html#setActivationRadius_float_) can be used to set the activation radius.

A [_View_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html) object connects to the [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) node in the scene graph, and specifies all viewing parameters of the rendering process of a 3D scene. Although it exists outside of the scene graph, it attaches to a [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) leaf node in the scene graph, using the method [_attachViewPlatform_(_ViewPlatform_ vp)](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html#attachViewPlatform_javax_media_j3d_ViewPlatform_). A [_View_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html) object contains references to a [_PhysicalBody_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/PhysicalBody.html) and a [_PhysicalEnvironment_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/PhysicalEnvironment.html) object, which can be set using the methods [_setPhysicalBody_()](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html#setPhysicalBody_javax_media_j3d_PhysicalBody_) and [_setPhysicalEnvironment_()](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html#setPhysicalEnvironment_javax_media_j3d_PhysicalEnvironment_)_, respectively_.

A [_View_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html) object contains a list of [_Canvas3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Canvas3D.html) objects where rendering of the view is done. The method [_addCanvas3D_(Canvas3D c)](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html#addCanvas3D_javax_media_j3d_Canvas3D_) of the class [_View_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html) can be used to add the provided [_Canvas3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Canvas3D.html) object to the list of canvases of the [View](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/View.html) object.

{{< resource "962db16a-d746-33a5-7a2a-a1311a65fb65" >}}

Class [_Canvas3D_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/Canvas3D.html) extends the heavyweight class [_Canvas_](http://java.sun.com/j2se/1.3/docs/api/java/awt/Canvas.html) in order to achieve hardware acceleration, since a low rendering library, such as OpenGL, requires the rendering to be done in a native window to enable hardware acceleration.

Finally, all [_Canvas3D_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/Canvas3D.html) objects on the same physical display device refer to a [_Screen3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Screen3D.html) object, which contains all information about that particular display device. [_Screen3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Screen3D.html) can be obtained from the [_Canvas3D_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/Canvas3D.html) using the [_getScreen3D_()](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Canvas3D.html#getScreen3D__) method.

Default Coordinate System
-------------------------

The default coordinate system is a right-handed Cartesian coordinate system centered on the screen with the x and y-axes directed towards the right and top of the screen, respectively. The z-axis is, by default directed out of the screen towards the viewer, as shown below. The default distances are in meter and the angles in radians.  
 

{{< resource "b4b7e83d-b897-f4fe-b33f-16f275d7751d" >}}  
  
Transformations

Class [_TransformGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransformGroup.html) which extends the class [_Group_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Group.html) can be used to set a spatial transformation, such as positioning, orientation, and scaling of its children through the use of a [_Transform3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Transform3D.html) object. A [_TransformGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransformGroup.html) node enables the setting and use of a coordinate system relative to its parent coordinate system.

The [_Transform3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Transform3D.html) object of a [_TransformGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransformGroup.html) object can be set using the method [_setTransform_(Transform3D  t)](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransformGroup.html#setTransform_javax_media_j3d_Transform3D_), which is used to set the transformation components of the [_Transform3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Transform3D.html) object to the ones of the passed parameter.

A [_Transform3D_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Transform3D.html) object is a 4x4 double-precision matrix that is used to determine the transformations of a [_TransformGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransformGroup.html) node, as shown in the following equation. The elements T{{< sub "00" >}}, T{{< sub "01" >}}, T{{< sub "02" >}}, T{{< sub "10" >}}, T{{< sub "11" >}}, T{{< sub "12" >}},T{{< sub "20" >}}, T{{< sub "21" >}}, and T{{< sub "22" >}} are used to set the rotation and scaling, and the T{{< sub "03" >}}, T{{< sub "13" >}}, and T{{< sub "23" >}} are used to set the translation.

{{< resource "339b4938-a492-82c1-5254-af6bded234ec" >}}

As the scene graph is traversed by the Java® 3D renderer, the transformations specified by any transformation nodes accumulate. The transformations closer to the geometry nodes executed prior to the ones closer to the virtual universe node.

{{< anchor "5" >}}{{< /anchor >}}5\. A Simple Java® 3D Program
--------------------------------------------------------------

A Java® 3D program builds a scene graph, using Java® 3D classes and methods, that can be rendered onto the screen.

The following program creates 2 color cubes and a sphere as shown to the snapshot that follows the code.

_import java.awt.\*;_  
_import javax.swing.\*;_  
_import javax.media.j3d.\*;_  
_import javax.vecmath.\*;_  
_import java.awt.event.\*;_  
_import com.sun.j3d.utils.geometry.\*;_

 _public class MyJava3D extends JFrame_  
_{_  
 _//  Virtual Universe object._  
 _private VirtualUniverse universe;_

 _//  Locale of the scene graph._  
 _private Locale locale;_  
 

 _// BranchGroup for the Content Branch of the scene_  
 _private BranchGroup contentBranch;_

 _//  TransformGroup  node of the scene contents_  
 _private TransformGroup contentsTransGr;_  
 

 _// BranchGroup for the View Branch of the scene_  
 _private BranchGroup viewBranch;_

 _// ViewPlatform node, defines from where the scene is viewed._  
 _private ViewPlatform viewPlatform;_

 _//  Transform group for the ViewPlatform node_  
 _private TransformGroup vpTransGr;_

 _//  View node, defines the View parameters._  
 _private View view;_

 _// A PhysicalBody object can specify the user's head_  
 _PhysicalBody body;_

 _// A PhysicalEnvironment object can specify the physical_  
 _// environment in which the view will be generated_  
 _PhysicalEnvironment environment;_

 _// Drawing canvas for 3D rendering_  
 _private Canvas3D canvas;_

 _// Screen3D Object contains screen's information_  
 _private Screen3D screen;_

 _private Bounds bounds;_  
 

 _public MyJava3D()_  
 _{_  
 _super("My First Java3D Example");_

 _// Creating and setting the Canvas3D_  
 _canvas = new Canvas3D(null);_  
 _getContentPane().setLayout( new BorderLayout( ) );_  
 _getContentPane().add(canvas, "Center");_

 _// Setting the VirtualUniverse and the Locale nodes_  
 _setUniverse();_

 _// Setting the content branch_  
 _setContent();_

 _// Setting the view branch_  
 _setViewing();_

 _// To avoid problems between Java3D and Swing_  
 _JPopupMenu.setDefaultLightWeightPopupEnabled(false);_

 _// enabling window closing_  
 _addWindowListener(new WindowAdapter() {_  
 _public void windowClosing(WindowEvent e)_  
 _{System.exit(0); }   });_  
 _setSize(600, 600);_  
 _bounds = new BoundingSphere(new Point3d(0.0,0.0,0.0), Double.MAX\_VALUE);_  
 _}_  
 

 _private void setUniverse()_  
 _{_  
 _// Creating the VirtualUniverse and the Locale nodes_  
 _universe = new VirtualUniverse();_  
 _locale = new Locale(universe);_  
 _}_

 _private void setContent()_  
 _{_  
 _// Creating the content branch_

 _contentsTransGr = new TransformGroup();_  
 _contentsTransGr.setCapability(TransformGroup.ALLOW\_TRANSFORM\_WRITE);_

 _setLighting();_

 _ColorCube cube1 = new ColorCube(0.1);_

 _Appearance appearance = new Appearance();_  
 _cube1.setAppearance(appearance);_

 _contentsTransGr.addChild(cube1);_  
 

 _ColorCube cube2 = new ColorCube(0.25);_

 _Transform3D t1 = new Transform3D();_  
 _t1.rotZ(0.5);_  
 _Transform3D t2 = new Transform3D();_  
 _t2.set(new Vector3f(0.7f, 0.6f,-1.0f));_  
 _t2.mul(t1);_  
 _TransformGroup trans2 = new TransformGroup(t2);_  
 _trans2.addChild(cube2);_  
 _contentsTransGr.addChild(trans2);_  
 

 _Sphere sphere = new Sphere(0.2f);_  
 _Transform3D t3 = new Transform3D();_  
 _t3.set(new Vector3f(-0.2f, 0.5f,-0.2f));_  
 _TransformGroup trans3 = new TransformGroup(t3);_

 _Appearance appearance3 = new Appearance();_

 _Material mat = new Material();_  
 _mat.setEmissiveColor(-0.2f, 1.5f, 0.1f);_  
 _mat.setShininess(5.0f);_  
 _appearance3.setMaterial(mat);_  
 _sphere.setAppearance(appearance3);_  
 _trans3.addChild(sphere);_  
 _contentsTransGr.addChild(trans3);_  
 

 _contentBranch = new BranchGroup();_  
 _contentBranch.addChild(contentsTransGr);_  
 _// Compiling the branch graph before making it live_  
 _contentBranch .compile();_

 _// Adding a branch graph into a locale makes its nodes live (drawable)_  
 _locale.addBranchGraph(contentBranch);_  
 _}_

 _private void setLighting()_  
 _{_  
 _AmbientLight ambientLight =  new AmbientLight();_  
 _ambientLight.setEnable(true);_  
 _ambientLight.setColor(new Color3f(0.10f, 0.1f, 1.0f) );_  
 _ambientLight.setCapability(AmbientLight.ALLOW\_STATE\_READ);_  
 _ambientLight.setCapability(AmbientLight.ALLOW\_STATE\_WRITE);_  
 _ambientLight.setInfluencingBounds(bounds);_  
 _contentsTransGr.addChild(ambientLight);_

 _DirectionalLight dirLight =  new DirectionalLight();_  
 _dirLight.setEnable(true);_  
 _dirLight.setColor( new Color3f( 1.0f, 0.0f, 0.0f ) );_  
 _dirLight.setDirection( new Vector3f( 1.0f, -0.5f, -0.5f ) );_  
 _dirLight.setCapability( AmbientLight.ALLOW\_STATE\_WRITE );_  
 _dirLight.setInfluencingBounds(bounds);_  
 _contentsTransGr.addChild(dirLight);_  
 _}_

 _private void setViewing()_  
 _{_  
 _// Creating the viewing branch_

 _viewBranch = new BranchGroup();_

 _// Setting the viewPlatform_  
 _viewPlatform = new ViewPlatform();_  
 _viewPlatform.setActivationRadius(Float.MAX\_VALUE);_  
 _viewPlatform.setBounds(bounds);_

 _Transform3D t = new Transform3D();_  
 _t.set(new Vector3f(0.3f, 0.7f, 3.0f));_  
 _vpTransGr = new TransformGroup(t);_

 _// Node capabilities control (granding permission) read and write access_  
 _//  after a node is live or compiled_  
 _//  The number of capabilities small to allow more optimizations during compilation_  
 _vpTransGr.setCapability(TransformGroup.ALLOW\_TRANSFORM\_WRITE);_  
 _vpTransGr.setCapability( TransformGroup.ALLOW\_TRANSFORM\_READ);_

 _vpTransGr.addChild(viewPlatform);_  
 _viewBranch.addChild(vpTransGr);_

 _// Setting the view_  
 _view = new View();_  
 _view.setProjectionPolicy(View.PERSPECTIVE\_PROJECTION );_  
 _view.addCanvas3D(canvas);_

 _body = new PhysicalBody();_  
 _view.setPhysicalBody(body);_  
 _environment = new PhysicalEnvironment();_  
 _view.setPhysicalEnvironment(environment);_

 _view.attachViewPlatform(viewPlatform);_

 _view.setWindowResizePolicy(View.PHYSICAL\_WORLD);_

 _locale.addBranchGraph(viewBranch);_  
 _}_

 _public static void main(String\[\] args)_  
 _{_  
 _JFrame frame = new MyJava3D();_  
 _frame.setVisible(true);_

 _}_  
_}_{{< resource "6b5587cd-656d-0bd0-fb79-7b5e50916d6c" >}}

A utility class, called _SimpleUniverse_, can alternatively be used to automatically build a common arrangement of a universe, locale, and viewing classes, avoiding the need to create explicitly the viewing branch. Then, a branch is added into the simple universe to make its nodes live (i.e. drawable).

_SimpleUniverse simpleUniverse = new SimpleUniverse(canvas);_  
_simpleUniverse.addBranchGraph(contentBranch);_

6\. More on Java® 3D
--------------------

_Java® 3D and Swing_

Since the [_Canvas3D_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/Canvas3D.html) extends the heavyweight AWT class [_Canvas_](https://www.oracle.com/webfolder/technetwork/data-quality/edqhelp/Content/ui/canvas/canvas.htm), it should be handled with care if Swing is used. The information provided when [_mixing AWT and Swing_](http://java.sun.com/products/jfc/tsc/swingdoc-archive/mixing.html)  components should be followed. The main problem is that there is one-to-one correspondence between heavyweight components and their window system peers, i.e. native OS window components. In contrast, a lightweight component expects to use the peer of its enclosing container since it does not have a peer.

When lightweight components overlap with heavyweight components, the heavyweight components are always painted on top. In general, the heavyweight [_Canvas3D_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/Canvas3D.html) of Java® 3D should be kept apart from lightweight Swing components using different containers to avoid problems.

To avoid heavyweight components overlapping _Swing_ popup menus, which are lightweight, the popup menus  can be forced to be heavyweight using the method _setLightWeightPopupEnabled()_ of the _JPopupMenu_ class.

Similarly, problems with tooltips can be avoided by invoking the following method

_ToolTipManager.sharedInstance().setLightWeightPopupEnabled(false)_

Behaviors
---------

Behaviors are essentially Java® methods that are scheduled to run only when certain requirements are satisfied according to wakeup conditions. Although a [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object is connected to the scene it is kept in a separate area of the Java® 3D runtime environment and it is not considered part of the scene graph. The runtime environment treats a [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object differently ensuring that certain actions take place. All behaviors in Java® 3D extend the [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) class, which is an abstract class that itself extends the [_Leaf_](http://java.sun.com/products/java-media/3D/forDevelopers/j3dapi/javax/media/j3d/Leaf.html) class. The [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) class provides a way to execute certain statements, provided in the [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method, in order to modify the scene graph when specified criteria are satisfied.

The [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) class has two major methods, in particular the [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__) method, which is called when the behavior becomes live, and the [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method, which is called by the Java® 3D scheduler whenever appropriate,  and  a scheduling region. Typically, in order to create a custom behavior, the class [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) is extended and referenced by the scene graph from an appropriate place that should be able to effect. A custom behavior that extends the [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) class should implement the [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__) and [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) methods, and provide other methods and constructors that may be needed. The [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) class object contains the state information that is needed by its [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__)and the [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) methods. A constructor or another method may be used to set references to the scene graph objects upon which the behavior acts. In addition, the [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) class is extended by the following three classes [_Billboard_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Billboard.html), [_Interpolator_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Interpolator.html), and [_LOD_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/LOD.html).

The [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__) method is called once when the behavior becomes "live", i.e. when its [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) node is added to a [_VirtualUniverse_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/VirtualUniverse.html), to initialize this behavior. The Java® 3D behavior scheduler calls the [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__) method, which should never be called directly. The [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__) method is used to set a [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object, which has been "added" to the scene graph, into a "known" condition and register the criteria to be used to decide on its execution. Classes that extend Behavior must provide their own [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__) method. The [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__) method allows a [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object to initialize its internal state and specify its initial wakeup conditions. Java® 3D automatically invokes a behavior's initialize code when a [_BranchGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/BranchGroup.html) node that contains the behavior is added to the virtual universe, i.e. becomes live. The [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__) method should return, since Java® 3D does not invoke the initialize method in a new thread, and therefore it must regain control. Finally, a wakeup condition must be set in order to be able to invoke the [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method of the behavior.

However, a [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object is considered active only when its scheduling bounds intersect the activation volume of a [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) node. Therefore, the scheduling bounds should be provided for a behavior in order to be able to receive stimuli. The scheduling bounds of a behavior can be specified as a bounded spatial volume, such as a sphere, using the method [_setSchedulingBounds(Bounds region)_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#setSchedulingBounds_javax_media_j3d_Bounds_). Bounds are used for selective scheduling to improve performance. Bounds are used to decide whether a behavior should be added to the list of scheduled behaviors.

The [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method is called whenever the wakeup criteria are satisfied and the ViewPlatform's activation region intersect with the Behavior's scheduling region. The method is called by the Java® 3D behavior scheduler when something happens that causes the behavior to execute. A stimulus, i.e. a notification, informs the behavior that it should execute its [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method. Therefore, applications should not call explicitly this method. Classes that extend the [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) class must provide their own  [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method. The scheduling region defines a spatial volume that serves to enable the scheduling of [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) nodes. A [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) node is active, i.e. it can receive stimuli, whenever its scheduling region intersects the activation volume of a [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html).

The Java® 3D behavior scheduler invokes the [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method of a Behavior node when its scheduling region intersects the  activation volume of a [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) node and all wakeup criteria  of that behavior are satisfied. Then, the statements in the [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method may perform any computations and actions, such as including the registration of state change information that could cause Java® 3D to wake other Behavior objects and modify node values within the scene graph, change the internal state of the behavior, specify its next wakeup conditions, and exit. It is allowed to a [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object to change its next trigger event. The [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method, typically, manipulates scene graph elements, as long as the associated capabilities bits are set accordingly. For example, a [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) node can be used to repeatedly modify a [_TransformGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransformGroup.html) node in order to animate the associated with the [_TransformGroup_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/TransformGroup.html) node objects.

The amount of work done in a [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus(java.util.Enumeration)#processStimulus_java_util_Enumeration_) method should be limited since the method may lower the frame rate of the renderer. Java® 3D assumes that [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) methods run to completion and if necessary they spawn threads.

The application must provide the [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object with references to those scene graph elements that the Behavior object will manipulate. This is achieved by providing those references as arguments to the constructor of the behavior when the [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object is created. Alternatively, the Behavior object itself can obtain access to the relevant scene graph elements either when Java® 3D invokes its [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__) method or each time Java® 3D invokes its [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method. Typically, the application provides references to the scene graph objects that a behavior should be able to access as arguments to its constructor when the [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) is instantiated.

Java® 3D assumes that [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) methods always run to completion and that if needed they can spawn threads. The structure of each [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) method consists of the following parts:

*   code to decode and extract references from the [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) enumeration that awoke the object
*   code to perform the manipulations associated with the [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html)
*   code to establish new [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) for this behavior
*   a path to exit, so that execution returns to the Java® 3D behavior scheduler

The [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) class is an abstract class that specifies a single wakeup condition. It is specialized to 14 different [_WakeupCriterion_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCriterion.html) subclasses and to 4 subclasses that can be used to create complex wakeup conditions using boolean logic combinations of individual  [_WakeupCriterion_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCriterion.html) objects. A Behavior node provides a [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) object to the Java® 3D behavior scheduler using its [_wakeupOn()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#wakeupOn_javax_media_j3d_WakeupCondition_) method. When that [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) is satisfied, while the scheduling region intersects the activation volume of a [_ViewPlatform_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/ViewPlatform.html) node, the behavior scheduler passes that same [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) back to the [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) via an enumeration.

Java® 3D provides the following wakeup criteria that [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) objects can use to specify a complex [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html). All of the following are subclasses of the [_WakeupCriterion_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCriterion.html) class, which itself is a subclass of the [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) class.

*   [_WakeupOnViewPlatformEntry:_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnViewPlatformEntry.html) when the center of a ViewPlatform enters a specified region
*   [_WakeupOnViewPlatformExit:_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnViewPlatformExit.html) when the center of a ViewPlatform exits a specified region
*   [_WakeupOnActivation_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnActivation.html): when a behavior is activated
*   [_WakeupOnDeactivation_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnDeactivation.html): when a behavior is deactivated
*   [_WakeupOnTransformChange_:](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnTransformChange.html) when a specified TransformGroup node's transform changes
*   [_WakeupOnCollisionEntry_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnCollisionEntry.html): when collision is detected between a specified Shape3D node's Geometry object and any other object
*   [_WakeupOnCollisionMovement_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnCollisionMovement.html): when movement occurs between a specified Shape3D node's Geometry object and any other object with which it collides
*   [_WakeupOnCollisionExit_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnCollisionExit.html): when a specified Shape3D node's Geometry object no longer collides with any other object
*   [_WakeupOnBehaviorPost_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnBehaviorPost.html): when a specified Behavior object posts a specific event
*   [_WakeupOnAWTEvent_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnAWTEvent.html)_:_ when a specified AWT event occurs, such as. a mouse press
*   [_WakeupOnElapsedTime_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnElapsedTime.html): when a specified time interval elapses
*   [_WakeupOnElapsedFrames:_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnElapsedFrames.html) when a specified number of frames have been drawn
*   [_WakeupOnSensorEntry:_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnSensorEntry.html) when the center of a specified Sensor enters a specified region
*   [_WakeupOnSensorExit_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnViewPlatformExit.html): when the center of a specified Sensor exits a specified region

A [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object constructs a [_WakeupCriterion_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCriterion.html) by providing the appropriate arguments, such as a reference to some scene graph object and a region of interest.

Multiple criteria can be combined using the following classes to form complex wakeup conditions.

*   [_WakeupOr_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOr.html): specifies any number of wakeup conditions logically ORed together
*   [_WakeupAnd_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupAnd.html): specifies any number of wakeup conditions logically ANDed together
*   [_WakeupOrOfAnds_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOrOfAnds.html): specifies any number of OR wakeup conditions logically ANDed together
*   [_WakeupAndOfOr:_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupAndOfOrs.html)  specifies any number of AND wakeup conditions logically ORed together

The class hierarchy of the [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) class is shown below:

{{< resource "76163ee3-f63d-c91c-3d9f-88be97281f08" >}}

The following code provides an example of setting a [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) object

    _public void initialize()_  
 _{_  
 _[WakeupCriterion](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCriterion.html) criteria\[\] = new WakeupCriterion\[2\];_  
 _criteria\[0\] = new [WakeupOnElapsedFrames(3)](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnElapsedFrames.html#WakeupOnElapsedFrames_int_);_  
 _criteria\[0\] = new [WakeupOnElapsedTime(500)](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnElapsedTime.html#WakeupOnElapsedTime_long_);_

 _[WakeupCondition](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) condition = new [WakeupOr](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOr.html)(criteria);_  
 _[wakeupOn(](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#wakeupOn_javax_media_j3d_WakeupCondition_)condition);_  
 _}_

A [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) node provides a [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html) object to the behavior scheduler via its [_wakeupOn()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#wakeupOn_javax_media_j3d_WakeupCondition_) method and the behavior scheduler provides an enumeration of that [_WakeupCondition_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupCondition.html). The [_wakeupOn()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#wakeupOn_javax_media_j3d_WakeupCondition_) method should be called from the [_initialize()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#initialize__) and [_processStimulus()_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus(java.util.Enumeration)) methods, just prior of exiting these methods.

In the current Java® 3D implementation the behavior scheduler, and, therefore, the [_processStimulus_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus(java.util.Enumeration)) method of the [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) class as well, run concurrently with the rendering thread. However, a new thread will not start until both the renderer, which may be working on the previous frame, and the behavior scheduler are done.

Java® 3D guarantees that all behaviors with a [_WakeupOnElapsedFrames_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/WakeupOnElapsedFrames.html) will be executed before the next frame starts rendering, i.e. the rendering thread will wait until all behaviors are done with their [_processStimulus_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) methods before drawing the next frame. In addition, Java® 3D guarantees that all scene graph updates that occur from within a single [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object will be reflected in the same frame for consistency purposes.

Finally, [_Interpolator_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Interpolator.html) objects can be used for simple behaviors where a parameter can be varied between a starting and an ending value during a certain time interval.

Lights
------

Lights can be used in order to achieve higher quality and realism of the graphics. Lighting capabilities is provided by the class Light and its subclasses. All light objects have a color, an on/off state, and a bounding volume that controls their illumination range. Java3D provides the following four types of lights, which are subclasses of the class [_Light_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Light.html):

*   _[AmbientLight](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/AmbientLight.html)_: the rays from an ambient light source object come from all directions illuminating shapes evenly
*   _[DirectionalLight](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/DirectionalLight.html)_: a directional light source object has parallel rays of light aiming at a certain direction
*   _[PointLight](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/PointLight.html)_: the rays from an point light source object are emitted radially from a point to all directions
*   _[SpotLight](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/SpotLight.html)_: the rays from a spot light source object are emitted radially from a point to all directions but within a cone

{{< anchor "6" >}}{{< /anchor >}}6\. Performance of Java® 3D
------------------------------------------------------------

Java® 3D aims at achieving high performance by utilizing the available graphics libraries (OpenGL/Direct3D), using 3D-graphics acceleration where available, and supporting some rendering optimizations (such as scene reorganization and content culling). It is optimized for performance rather than quality of image rendering. Compilation of branch groups and utilization of capability bits enable speed optimizations. It is as fast and high-level as Open Inventor and VRML (Virtual Reality Modeling Language), while it offers the portability of Java® and the direct access and well integration with all other available Java® APIs. Java® 3D uses native code of certain libraries, such as the OpenGL, at the final steps of rendering to achieve satisfactory performance levels. A scene reorganization and a content culling may be used by the renderer to optimize rendering by following an optimal order that bypasses hidden parts of the scene.

Java® 3D rendering is tuned to the underlying hardware utilizing a wide range of hardware and software platforms. Java® 3D is scalable, taking advantage of multithreading capabilities of Java® when multiple processors are available. The availability of multiple processors is automatically utilized by its independent and asynchronous components, such as the rendering thread and the behavior scheduler, that can be assigned to different processors. Also, branches of the scene tree-structure can be manipulated independently and concurrently utilizing multithreading and multiprocessing.

A thread scheduler was implemented inside the Java® 3D, providing to the Java® 3D architects full control of all threads and eliminating the need to deal with thread priorities. the underlying architecture uses messages to propagate scnegraph changes into certain structures that are used to optimize a particular functionality. There are two structures for geometric objects. The one organizes the geometry spatially enabling spatial queries on the scene graph, such as picking, collisions, culling etc. The other structure is a state snapshot of the scene graph, known as render bin, which is associated with each view and is used by the renderer thread. There is also a structure associated with behaviors that spatially organizes behavior nodes, and a behavior scheduler thread that executes behaviors that need to be executed.

The thread scheduler is essentially in a big infinite loop implemented inside the Java® 3D. For each iteration, the thread scheduler runs each thread that needs to be run once, waiting for all threads to be completed before entering the next iteration. The behavior and the rendering threads may run once in a single iteration. The following operations are conceptually performed within this infinite loop.

 _while(true)_  
 _{_  
 _process input_

 _if(there is a request for exit)_  
 _break_

 _perform any behaviors_

 _transverse scene graph and render visible objects_  
 _}_

Whenever a node of the scene graph is modified a message is generated with a value associated with it and any state necessary to reflect the specific changes, and queued with all other messages by the thread scheduler. At each iteration the messages are processed and the various structures are updated accordingly. The update time is very fast when the messages are very simple, which is typically the case. In the current implementation the rendering thread and the behavior thread can run concurrently. In particular, the behavior scheduler and therefore the [_processStimulus_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html#processStimulus_java_util_Enumeration_) method of a [_Behavior_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/Behavior.html) object, can run concurrently with the renderer. However, a new frame will not start until both the rendering of the previous frame and the behavior scheduler are done.

Finally it offers level-of-detail ([_LOD_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/LOD.html)) capabilities to further improve performance using a [_LOD_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/LOD.html) object. An LOD leaf node is an abstract class that operates on a list of Switch group nodes to select one of the children of the Switch nodes. The [_LOD_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/LOD.html) class is extended to implement various selection criteria, such as the [_DistanceLOD_](http://java.sun.com/products/java-media/3D/forDevelopers/J3D_1_2_API/j3dapi/javax/media/j3d/DistanceLOD.html) subclass.