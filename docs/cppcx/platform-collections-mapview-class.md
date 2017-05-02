---
title: "Platform::Collections::MapView-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView-Klasse"
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Collections::MapView-Klasse
Stellt eine schreibgeschützte Ansicht einer *Zuordnung* dar, die eine Auflistung von Schlüssel\-Wert\-Paaren ist.  
  
## Syntax  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = ::std::less<K>  
>  
ref class MapView sealed;  
```  
  
#### Parameter  
 `K`  
 Der Typ des Schlüssels im Schlüssel\-Wert\-Paar.  
  
 `V`  
 Der Typ des Werts im Schlüssel\-Wert\-Paar.  
  
 `C`  
 Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in der MapView zu bestimmen. Standardmäßig [::std::less\<K\>](../standard-library/less-struct.md).  
  
## Hinweise  
 MapView ist eine konkrete C\+\+\-Implementierung der Schnittstelle [Windows::Foundation::Collections::IMapView \<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262409), die über die Anwendungsbinärdateischnittstelle \(ABI\) übergeben wird. Weitere Informationen finden Sie unter [Auflistungen \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[MapView::MapView\-Konstruktor](../cppcx/mapview-mapview-constructor.md)|Initialisiert eine neue Instanz der MapView\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[MapView::First\-Methode](../cppcx/mapview-first-method.md)|Gibt einen Iterator zurück, der mit dem ersten Element der Zuordnungsansicht initialisiert wird.|  
|[MapView::HasKey\-Methode](../cppcx/mapview-haskey-method.md)|Ermittelt, ob die aktuelle MapView den angegebenen Schlüssel enthält.|  
|[MapView::Lookup\-Methode](../cppcx/mapview-lookup-method.md)|Ruft das Element am angegebenen Schlüssel im aktuellen MapView\-Objekt ab.|  
|[MapView::Size\-Methode](../cppcx/mapview-size-method.md)|Gibt die Anzahl von Elementen im aktuellen MapView\-Objekt zurück.|  
|[MapView::Split\-Methode](../cppcx/mapview-split-method.md)|Teilt ein Original\-MapView\-Objekt in zwei MapView\-Objekte.|  
  
## Vererbungshierarchie  
 `MapView`  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)