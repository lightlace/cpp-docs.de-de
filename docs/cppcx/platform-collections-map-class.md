---
title: "Platform::Collections::Map-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map-Klasse (C++/Cx)"
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
caps.latest.revision: 19
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 19
---
# Platform::Collections::Map-Klasse
Stellt eine *Zuordnung* dar, die eine Auflistung von Schlüssel\-Wert\-Paaren ist.  
  
## Syntax  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = std::less<K>  
ref class Map sealed;  
```  
  
#### Parameter  
 `K`  
 Der Typ des Schlüssels im Schlüssel\-Wert\-Paar.  
  
 `V`  
 Der Typ des Werts im Schlüssel\-Wert\-Paar.  
  
 `C`  
 Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in der Map zu bestimmen. Standardmäßig [std::less\<K\>](../standard-library/less-struct.md).  
  
 \_\_is\_valid\_winrt\_type\(\)  
 Eine vom Compiler generierte Funktion, die den Typ von K und V überprüft und eine benutzerfreundliche Fehlermeldung ausgibt, wenn der Typ nicht in der Zuordnung gespeichert werden kann.  
  
## Hinweise  
 Zulässige Typen sind:  
  
-   Ganze Zahlen  
  
-   Schnittstellenklasse ^  
  
-   Öffentliche Referenzklasse^  
  
-   value struct  
  
-   Öffentliche Enumerationsklasse  
  
 Die Zuordnung ist im Grunde genommen ein Wrapper für [std::map](../standard-library/map-class.md). Es handelt sich um eine konkrete C\+\+\-Implementierung der Typen [Windows::Foundation::Collections::IMap\<Windows::Foundation::Collections::IKeyValuePair\<K,V\>\>](http://go.microsoft.com/fwlink/p/?LinkId=262408) und [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx), die über öffentliche [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Schnittstellen übergeben werden. Wenn Sie versuchen, einen `Platform::Collections::Map`\-Typ in einem öffentlichen Rückgabewert oder Parameter zu verwenden, wird der Compilerfehler C3986 ausgelöst. Sie können den Fehler beheben, indem Sie den Typ des Parameters oder des Rückgabewerts in [Windows::Foundation::Collections::IMap\<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262408) ändern.  
  
 Weitere Informationen finden Sie unter [Auflistungen](../cppcx/collections-c-cx.md).  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Map::Map\-Konstruktor](../cppcx/map-map-constructor.md)|Initialisiert eine neue Instanz der Map\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Map::Clear\-Methode](../cppcx/map-clear-method.md)|Entfernt alle Schlüssel\-Wert\-Paare aus dem derzeitigen Map\-Objekt.|  
|[Map::First\-Methode](../cppcx/map-first-method.md)|Gibt einen Iterator zurück, der das erste Element in der Zuordnung angibt.|  
|[Map::GetView\-Methode](../cppcx/map-getview-method.md)|Gibt eine schreibgeschützte Ansicht der aktuellen Zuordnung zurück; das heißt, eine [Platform::Collections::MapView\-Klasse](../cppcx/platform-collections-mapview-class.md).|  
|[Map::HasKey\-Methode](../cppcx/map-haskey-method.md)|Ermittelt, ob die aktuelle Map den angegebenen Schlüssel enthält.|  
|[Map::Insert\-Methode](../cppcx/map-insert-method.md)|Fügt das angegebene Schlüssel\-Wert\-Paar dem aktuellen Map\-Objekt hinzu.|  
|[Map::Lookup\-Methode](../cppcx/map-lookup-method.md)|Ruft das Element am angegebenen Schlüssel im aktuellen Map\-Objekt ab.|  
|[Map::Remove\-Methode](../cppcx/map-remove-method.md)|Löscht das angegebene Schlüssel\-Wert\-Paar vom aktuellen Map\-Objekt.|  
|[Map::Size\-Methode](../cppcx/map-size-method.md)|Gibt die Anzahl von Elementen im aktuellen Map\-Objekt zurück.|  
  
### Ereignisse  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[Map::MapChanged\-Ereignis](../cppcx/map-mapchanged-event.md) `event`|Tritt auf, wenn sich die Map ändert.|  
  
## Vererbungshierarchie  
 `Map`  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md)