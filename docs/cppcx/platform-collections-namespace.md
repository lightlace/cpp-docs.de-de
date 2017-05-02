---
title: "Platform::Collections-Namespace | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Collections-Namespace"
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Collections-Namespace
Der Namespace Platform::Collections enthält die Klassen `Map`, `MapView`, `Vector` und `VectorView`. Diese Klassen sind konkrete Implementierungen der entsprechenden Schnittstellen, die im Namespace [Windows::Foundation::Collections](http://go.microsoft.com/fwlink/p/?LinkId=262645) definiert sind. Die konkreten Auflistungstypen können nicht über die ABI hinweg portiert werden \(z. B. beim Aufruf eines Javascript\- oder C\#\-Programms in eine C\+\+\-Komponente\). Sie sind allerdings implizit in ihre entsprechenden Schnittstellentypen konvertierbar. Wenn Sie z. B. eine öffentliche Methode implementieren, die eine Auflistung füllt und zurückgibt, verwenden Sie [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md), um die Auflistung intern zu implementieren. Verwenden Sie [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) als Rückgabetyp. Weitere Informationen finden Sie unter [Auflistungen](../cppcx/collections-c-cx.md) und [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md).  
  
 Sie können Platform::Collections::Vector aus [std::vector](../Topic/vector%20Class%201.md) und [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) aus [std::map](../standard-library/map-class.md) erstellen.  
  
 Darüber hinaus bietet der Namespace Platform::Collections Unterstützung für Rückeinfüge\- und Eingabe\-Iteratoren sowie für `Vector` und `VectorView`\-Iteratoren.  
  
 Sie müssen den Header "collection.h" einschließen \(`#include`\), um die Typen im Namespace Platform::Collections zu verwenden.  
  
## Syntax  
  
```cpp  
  
#include <collection.h>  
using namespace Platform::Collection;  
```  
  
## Mitglieder  
 Dieser Namespace enthält die folgenden Member.  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Platform::Collections::BackInsertIterator\-Klasse](../cppcx/platform-collections-backinsertiterator-class.md)|Stellt einen Iterator dar, der ein Element am Ende einer Auflistung einfügt.|  
|[Platform::Collections::InputIterator\-Klasse](../cppcx/platform-collections-inputiterator-class.md)|Stellt einen Iterator dar, der ein Element am Anfang einer Auflistung einfügt.|  
|[Platform::Collections::Map\-Klasse](../cppcx/platform-collections-map-class.md)|Stellt eine änderbare Auflistung von Schlüssel\-Wert\-Paaren dar, auf die über einen Schlüssel zugegriffen wird. Wie bei [std::map](../standard-library/map-class.md).|  
|[Platform::Collections::MapView\-Klasse](../cppcx/platform-collections-mapview-class.md)|Stellt eine schreibgeschützte Auflistung von Schlüssel\-Wert\-Paaren dar, auf die über einen Schlüssel zugegriffen wird.|  
|[Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md)|Stellt eine änderbare Sequenz von Elementen dar. Wie bei [std::vector](../Topic/vector%20Class%201.md).|  
|[Platform::Collections::VectorIterator\-Klasse](../cppcx/platform-collections-vectoriterator-class.md)|Stellt einen Iterator dar, der eine `Vector`\-Auflistung durchläuft.|  
|[Platform::Collections::VectorView\-Klasse](../cppcx/platform-collections-vectorview-class.md)|Stellt eine schreibgeschützte Sequenz von Elementen dar.|  
|[Platform::Collections::VectorViewIterator\-Klasse](../cppcx/platform-collections-vectorviewiterator-class.md)|Stellt einen Iterator dar, der eine `VectorView`\-Auflistung durchläuft.|  
  
## Vererbungshierarchie  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)  
  
## Anforderungen  
 **Metadaten:** platform.winmd  
  
 **Namespace:** Platform::Collections  
  
 **Compileroption:** \/ZW  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)