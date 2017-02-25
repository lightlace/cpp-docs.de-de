---
title: "ATL-Auflistungen und -Enumerationen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Collection-Schnittstellen"
  - "Auflistungen, ATL-Klassen"
  - "Enumerator-Schnittstellen"
  - "Enumeratoren, ATL-Klassen"
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ATL-Auflistungen und -Enumerationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`collection` ist ein COM\-Objekt, das eine Schnittstelle bereitstellt, die den Zugriff auf eine Gruppe Datenelementen zulässig \(Rohdaten oder andere Objekte\).  Eine Schnittstelle, die den Standards zum bietet Zugriff sowohl auf eine Gruppe von Objekten folgt, wird als *Auflistungsschnittstelle*.  
  
 müssen mindestens eine Auflistungsschnittstellen **Count**\-Eigenschaft bereitstellen, die die Anzahl der Elemente in der Auflistung, in einer **Item**\-Eigenschaft, die ein Element aus der Auflistung auf der Grundlage eines Index zurückgibt und in einer `_NewEnum`\-Eigenschaft zurückgibt, die einen Enumerator für die Auflistung zurückgibt.  Optional können **Hinzufügen**\-Auflistungsschnittstellen und **Remove**\-Methoden bereitstellen, um die Elemente zu ermöglichen, in eingefügt werden, oder von der Auflistung gelöscht und eine **Clear**\-Methode, um alle Elemente zu entfernen.  
  
 `enumerator` ist ein COM\-Objekt, das eine Schnittstelle zum Durchlaufen von Elementen in einer Auflistung bereitstellt.  Enumeratorschnittstellen seriellen bieten Zugriff auf Elemente einer Auflistung über vier erforderlichen Methoden: `Next`, **Skip**, **Zurücksetzen** und `Clone`.  
  
 Sie können mehr über Enumeratorschnittstellen durch Lesen über die archetypische \(jedoch vollständig imaginäre\)[IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\-Schnittstelle erfahren.  
  
## In diesem Abschnitt  
 [ATL\-Auflistungs\- und \-Enumerator\-Klassen](../atl/atl-collection-and-enumerator-classes.md)  
 Kurz beschreibt und enthält Links zu den ATL\-Klassen bereit, die Ihnen helfen, Auflistungen zu implementieren und Enumeratoren.  
  
 [Entwurfsprinzipien für Auflistungs\- und Enumerator\-Schnittstellen](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 Erläutert die unterschiedlichen Entwurfsprinzipien hinter jedem Typ Schnittstelle.  
  
 [Implementieren einer STL\-Basierten Auflistung](../atl/implementing-an-stl-based-collection.md)  
 Ein fortgeschrittenes Beispiel, das Sie über die Implementierung einer basierten Auflistung der Standardvorlagenbibliothek \(STL\) durchlaufen wird.  
  
## Verwandte Abschnitte  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Enthält Links zu konzeptionellen Themen darüber, wie mit Active Template Library Programmierung.  
  
 [ATLCollections\-Beispiel](../top/visual-cpp-samples.md)  
 Ein Beispiel, das die Verwendung von `ICollectionOnSTLImpl` und von `CComEnumOnSTL` wird und die Implementierung von benutzerdefinierten Kopierrichtlinienklassen.  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)