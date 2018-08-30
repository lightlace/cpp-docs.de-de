---
title: ATL und der freethreaded Marshaller | Microsoft-Dokumentation
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
ms.openlocfilehash: 6fa2e03bbb7307b2bc9633c21510f3b1939d4ad9
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218047"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL und der freethreaded Marshaller
Der ATL-Assistent für einfache Objekte die Seite "Attribute" bietet eine Option, die Ihre Klasse die freethreaded Marshaller (FTM) aggregieren kann.  
  
 Der Assistent generiert Code zum Erstellen einer Instanz von FTM in `FinalConstruct` und gibt diese Instanz in `FinalRelease`. Ein COM_INTERFACE_ENTRY_AGGREGATE-Makro wird automatisch hinzugefügt, um sicherzustellen, dass die COM-Zuordnung `QueryInterface` Anforderungen für [IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal) werden von der freethreaded Marshaller behandelt.  
  
 FTM bietet direkten Zugriff auf Schnittstellen für das Objekt von jedem Thread im selben Prozess, apartmentübergreifende Aufrufe beschleunigen. Diese Option ist für Klassen vorgesehen, die sowohl das Threadingmodell zu verwenden.  
  
 Wenn Sie diese Option verwenden zu können, müssen Klassen Verantwortung für die Threadsicherheit ihrer Daten ausführen. Darüber hinaus müssen Objekte, die die freethreaded Marshaler aggregiert und Schnittstellenzeiger abgerufen, die von anderen Objekten verwenden müssen zusätzliche Schritte, stellen Sie sicher, dass die Schnittstellen ordnungsgemäß gemarshallt werden. In der Regel umfasst das Speichern von den Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) und die Zeiger aus der GIT jedes Mal, wenn er verwendet wird. ATL stellt die Klasse [CComGITPtr](../atl/reference/ccomgitptr-class.md) zur Verwendung gespeichert, in der GIT-Schnittstellenzeiger auf.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](/windows/desktop/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)   
 [IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal)   
 [Verwenden Sie die globale Schnittstellentabelle](/windows/desktop/com/when-to-use-the-global-interface-table)   
 [In-Process-Server, Threadingprobleme](/windows/desktop/com/in-process-server-threading-issues)

