---
title: "Platform::Collections::UnorderedMap-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap"
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Collections::UnorderedMap-Klasse
Stellt eine ungeordnete *Zuordnung* dar, die eine Auflistung von Schlüssel\-Wert\-Paaren ist.  
  
## Syntax  
  
```scr  
template <  
   typename K,  
   typename V,  
   typename C = std::equal_to<K>  
>  
ref class Map sealed;  
```  
  
#### Parameter  
 `K`  
 Der Typ des Schlüssels im Schlüssel\-Wert\-Paar.  
  
 `V`  
 Der Typ des Werts im Schlüssel\-Wert\-Paar.  
  
 `C`  
 Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in der Map zu bestimmen. Standardmäßig [std::equal\_to\<K\>](../standard-library/equal-to-struct.md).  
  
## Hinweise  
 Zulässige Typen sind:  
  
-   Ganze Zahlen  
  
-   Schnittstellenklasse ^  
  
-   Öffentliche Referenzklasse^  
  
-   value struct  
  
-   Öffentliche Enumerationsklasse  
  
 UnorderedMap ist im Grunde genommen ein Wrapper für [std::unordered\_map](../standard-library/unordered-map-class.md), der die Speicherung von [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen unterstützt. Ist die konkrete Implementierung der Typen [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408) und [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx), die über öffentliche [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Schnittstellen übergeben werden. Wenn Sie versuchen, einen Platform::Collections::UnorderedMap\-Typ in einem öffentlichen Rückgabewert oder Parameter zu verwenden, wird der Compilerfehler C3986 ausgelöst. Sie können den Fehler beheben, indem Sie den Typ des Parameters oder des Rückgabewerts auf [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408) ändern.  
  
 Weitere Informationen finden Sie unter [Auflistungen](../cppcx/collections-c-cx.md).  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|UnorderedMap::UnorderedMap\-Konstruktor|Initialisiert eine neue Instanz der Map\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[UnorderedMap::Clear\-Methode](../cppcx/unorderedmap-clear-method.md)|Entfernt alle Schlüssel\-Wert\-Paare aus dem derzeitigen Map\-Objekt.|  
|[UnorderedMap::First\-Methode](../cppcx/unorderedmap-first-method.md)|Gibt einen Iterator zurück, der das erste Element in der Zuordnung angibt.|  
|[UnorderedMap::GetView\-Methode](../cppcx/unorderedmap-getview-method.md)|Gibt eine schreibgeschützte Ansicht der aktuellen Zuordnung zurück; das heißt, eine Platform::Collections::UnorderedMapView\-Klasse.|  
|[UnorderedMap::HasKey\-Methode](../cppcx/unorderedmap-haskey-method.md)|Ermittelt, ob die aktuelle Map den angegebenen Schlüssel enthält.|  
|[UnorderedMap::Insert\-Methode](../cppcx/unorderedmap-insert-method.md)|Fügt das angegebene Schlüssel\-Wert\-Paar dem aktuellen Map\-Objekt hinzu.|  
|[UnorderedMap::Lookup\-Methode](../cppcx/unorderedmap-lookup-method.md)|Ruft das Element am angegebenen Schlüssel im aktuellen Map\-Objekt ab.|  
|[UnorderedMap::Remove\-Methode](../cppcx/unorderedmap-remove-method.md)|Löscht das angegebene Schlüssel\-Wert\-Paar vom aktuellen Map\-Objekt.|  
|[UnorderedMap::Size\-Methode](../cppcx/unorderedmap-size-method.md)|Gibt die Anzahl von Elementen im aktuellen Map\-Objekt zurück.|  
  
### Ereignisse  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[Map::MapChanged\-Ereignis](../cppcx/map-mapchanged-event.md) `event`|Tritt auf, wenn sich die Map ändert.|  
  
## Vererbungshierarchie  
 `UnorderedMap`  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Platform::Collections\-Namespace](../cppcx/platform-collections-namespace.md)   
 [Platform::Collections::Map\-Klasse](../cppcx/platform-collections-map-class.md)   
 [Platform::Collections::UnorderedMapView\-Klasse](../cppcx/platform-collections-unorderedmapview-class.md)   
 [Auflistungen](../cppcx/collections-c-cx.md)   
 [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)