---
title: "Platform::Collections::UnorderedMapView-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView"
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::Collections::UnorderedMapView-Klasse
Stellt eine schreibgeschützte Ansicht einer *Zuordnung* dar, die eine Auflistung von Schlüssel\-Wert\-Paaren ist.  
  
## Syntax  
  
```cpp  
template <  
   typename K,  
   typename V,  
   typename C = ::std::equal_to<K>  
>  
ref class UnorderedMapView sealed;  
```  
  
#### Parameter  
 `K`  
 Der Typ des Schlüssels im Schlüssel\-Wert\-Paar.  
  
 `V`  
 Der Typ des Werts im Schlüssel\-Wert\-Paar.  
  
 `C`  
 Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Schlüsselwerte vergleichen kann, um deren Gleichzeit zu bestimmen. Standardmäßig [std::equal\_to\<K\>](../standard-library/equal-to-struct.md)  
  
## Hinweise  
 UnorderedMapView ist eine konkrete C\+\+\-Implementierung der Schnittstelle [Windows::Foundation::Collections::IMapView\<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262409), die über die Anwendungsbinärdateischnittstelle \(ABI\) übergeben wird. Weitere Informationen finden Sie unter [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[UnorderedMapView::UnorderedMapView\-Konstruktor](../cppcx/unorderedmapview-unorderedmapview-constructor.md)|Initialisiert eine neue Instanz der UnorderedMapView\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[UnorderedMapView::First\-Methode](../cppcx/unorderedmapview-first-method.md)|Gibt einen Iterator zurück, der mit dem ersten Element der Zuordnungsansicht initialisiert wird.|  
|[UnorderedMapView::HasKey\-Methode](../cppcx/unorderedmapview-haskey-method.md)|Ermittelt, ob die aktuelle UnorderedMapView den angegebenen Schlüssel enthält.|  
|[UnorderedMapView::Lookup\-Methode](../cppcx/unorderedmapview-lookup-method.md)|Ruft das Element am angegebenen Schlüssel im aktuellen UnorderedMapView\-Objekt ab.|  
|[UnorderedMapView::Size\-Methode](../cppcx/unorderedmapview-size-method.md)|Gibt die Anzahl von Elementen im aktuellen UnorderedMapView\-Objekt zurück.|  
|[UnorderedMapView::Split\-Methode](../cppcx/unorderedmapview-split-method.md)|Teilt ein originales UnorderedMapView\-Objekt in zwei UnorderedMapView\-Objekte.|  
  
## Vererbungshierarchie  
 `UnorderedMapView`  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections\-Namespace](../cppcx/platform-collections-namespace.md)   
 [Windows::Foundation::IMapView](http://go.microsoft.com/fwlink/p/?LinkId=262409)