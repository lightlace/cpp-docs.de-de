---
title: ATL und der freethreaded Marshaller | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1716985adf65b714a418f20d3873f45c32d368b4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL und der freethreaded Marshaller
Der ATL-Assistent für einfache Objekte der Seite "Attribute" bietet eine Option, die Ihre Klasse der freethreaded Marshaller (FTM) aggregieren kann.  
  
 Der Assistent generiert Code zum Erstellen einer Instanz von der freethreaded Marshaller in `FinalConstruct` und gibt diese Instanz in `FinalRelease`. Ein `COM_INTERFACE_ENTRY_AGGREGATE` Makro wird automatisch hinzugefügt, um sicherzustellen, dass die COM-Zuordnung `QueryInterface` Anforderungen für [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707) werden von der freethreaded Marshaller behandelt.  
  
 Freethreaded Marshaler ermöglicht den direkten Zugriff auf Schnittstellen für das Objekt von jedem Thread im selben Prozess apartmentübergreifende Aufrufe beschleunigen. Diese Option ist für Klassen vorgesehen, die beide Threadingmodell verwenden.  
  
 Wenn Sie diese Option verwenden zu können, müssen Klassen Verantwortung für die Threadsicherheit ihrer Daten übernehmen. Darüber hinaus müssen Objekte, die die freethreaded Marshaler aggregiert und Schnittstellenzeigern abgerufen, die von anderen Objekten verwenden müssen zusätzliche Schritte Unternehmen, stellen Sie sicher, dass die Schnittstellen richtig gemarshallt werden. In der Regel umfasst dies Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) speichern und Abrufen von des Zeigers aus der GIT jedes Mal, die sie verwendet wird. ATL stellt die Klasse [CComGITPtr](../atl/reference/ccomgitptr-class.md) lassen sich in der GIT gespeicherten Schnittstellenzeigern verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [Verwenden der globalen Schnittstellentabelle](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [In-Process-Server Threadingprobleme](http://msdn.microsoft.com/library/windows/desktop/ms687205)

