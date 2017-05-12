---
title: "Platform::Collections::VectorView-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView-Klasse"
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Platform::Collections::VectorView-Klasse
Stellt eine schreibgeschützte Ansicht einer sequenziellen Auflistung von Objekten dar, auf die einzeln nach Index zugegriffen werden kann. Der Typ der einzelnen Objekte in der Auflistung wird durch den Vorlagenparameter spezifiziert.  
  
## Syntax  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### Parameter  
 `T`  
 Der Typ der im `VectorView`\-Objekt enthaltenen Elemente.  
  
 `E`  
 Gibt ein binäres Prädikat zum Testen der Übereinstimmung mit Werten des Typs `T` an. Der Standardwert ist `std::equal_to<T>`.  
  
## Hinweise  
 Die Klasse `VectorView` implementiert die Schnittstelle [Windows::Foundation::Collections::IVectorView\<T\>](http://go.microsoft.com/fwlink/p/?LinkId=262411) sowie Unterstützung für Standardvorlagenbibliotheksiteratoren.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[VectorView::VectorView\-Konstruktor](../cppcx/vectorview-vectorview-constructor.md)|Initialisiert eine neue Instanz der VectorView\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[VectorView::First\-Methode](../cppcx/vectorview-first-method.md)|Gibt einen Iterator zurück, der das erste Element in der VectorView angibt.|  
|[VectorView::GetAt\-Methode](../cppcx/vectorview-getat-method.md)|Ruft das Element der aktuellen VectorView ab, das durch den angegebenen Index bezeichnet wird.|  
|[VectorView::GetMany\-Methode](../cppcx/vectorview-getmany-method.md)|Ruft eine Sequenz von Elementen von der aktuellen VectorView ab, die am angegebenen Index beginnt.|  
|[VectorView::IndexOf\-Methode](../cppcx/vectorview-indexof-method.md)|Sucht das angegebene Element in der aktuellen VectorView und gibt, wenn es gefunden wurde, den Index des Elements zurück.|  
|[VectorView::Size\-Methode](../cppcx/vectorview-size-method.md)|Gibt die Anzahl von Elementen im aktuellen VectorView\-Objekt zurück.|  
  
## Vererbungshierarchie  
 `VectorView`  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)