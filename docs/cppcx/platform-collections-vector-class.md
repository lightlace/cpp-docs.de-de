---
title: "Platform::Collections::Vector-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vektorklasse (C++/Cx)"
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 17
---
# Platform::Collections::Vector-Klasse
Stellt eine sequenzielle Auflistung von Objekten dar, auf die einzeln über einen Index zugegriffen werden kann.  
  
## Syntax  
  
```  
template <typename T, typename E>  
   ref class Vector sealed;  
```  
  
#### Parameter  
 `T`  
 Der Typ der im Vektorobjekt enthaltenen Elemente.  
  
 `E`  
 Gibt ein binäres Prädikat zum Testen der Übereinstimmung mit Werten des Typs `T` an. Der Standardwert ist `std::equal_to<T>`.  
  
## Hinweise  
 Zulässige Typen sind:  
  
1.  Ganze Zahlen  
  
2.  Schnittstellenklasse ^  
  
3.  Öffentliche Referenzklasse^  
  
4.  value struct  
  
5.  Öffentliche Enumerationsklasse  
  
 Die Vektorklasse ist die konkrete C\+\+ Implementierung der [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410)\-Schnittstelle.  
  
 Wenn Sie versuchen, einen Vector\-Typ in einem öffentlichen Rückgabewert oder Parameter zu verwenden, wir der Compilerfehler C3986 ausgelöst. Sie können den Fehler beheben, indem Sie den Typ des Parameters oder des Rückgabewerts in [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) ändern. Weitere Informationen finden Sie unter [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Vector::Vector\-Konstruktor](../cppcx/vector-vector-constructor.md)|Initialisiert eine neue Instanz der Vector\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Vector::Append\-Methode](../cppcx/vector-append-method.md)|Fügt das angegebene Element nach dem letzten Element im aktuellen Vektor ein.|  
|[Vector::Clear\-Methode](../cppcx/vector-clear-method.md)|Löscht alle Elemente im aktuellen Vector.|  
|[Vector::First\-Methode](../cppcx/vector-first-method.md)|Gibt einen Iterator zurück, der das erste Element im Vektor angibt.|  
|[Vector::GetAt\-Methode](../cppcx/vector-getat-method.md)|Ruft das Element des aktuellen Vector ab, das durch den angegebenen Index bezeichnet wird.|  
|[Vector::GetMany\-Methode](../cppcx/vector-getmany-method.md)|Ruft eine Sequenz von Elementen vom aktuellen Vektor ab, die am angegebenen Index beginnt.|  
|[Vector::GetView\-Methode](../cppcx/vector-getview-method.md)|Gibt eine schreibgeschützte Ansicht eines Vektors zurück; also [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md).|  
|[Vector::IndexOf\-Methode](../cppcx/vector-indexof-method.md)|Sucht das angegebene Element im aktuellen Vector und gibt, wenn es gefunden wurde, den Index des Elements zurück.|  
|[Vector::InsertAt\-Methode](../cppcx/vector-insertat-method.md)|Fügt das angegebene Element in den aktuellen Vector nach dem Element ein, das durch den angegebenen Index identifiziert wird.|  
|[Vector::ReplaceAll\-Methode](../cppcx/vector-replaceall-method.md)|Löscht die Elemente im aktuellen Vektor und fügt dann die Elemente aus dem angegebenen Array ein.|  
|[Vector::RemoveAt\-Methode](../cppcx/vector-removeat-method.md)|Löscht das Element, das durch den angegebenen Index von dem aktuellen Vektor identifiziert wird.|  
|[Vector::RemoveAtEnd\-Methode](../cppcx/vector-removeatend-method.md)|Löscht das Element am Ende des aktuellen Vektors.|  
|[Vector::SetAt\-Methode](../cppcx/vector-setat-method.md)|Weist den angegebenen Wert dem Element im aktuellen Vektor zu, der vom angegebenen Index identifiziert wird.|  
|[Vector::Size\-Methode](../cppcx/vector-size-method.md)|Gibt die Anzahl von Elementen im aktuellen Vector\-Objekt zurück.|  
  
### Ereignisse  
  
|||  
|-|-|  
|Name|Beschreibung|  
|Ereignis [Windows::Foundation::Collection::VectorChangedEventHandler\<T\>^ VectorChanged](http://go.microsoft.com/fwlink/p/?LinkId=262644)|Tritt auf, wenn sich der Vektor ändert.|  
  
## Vererbungshierarchie  
 `Vector`  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)