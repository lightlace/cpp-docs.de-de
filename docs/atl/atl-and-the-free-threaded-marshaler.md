---
title: ATL und der freethreaded Marshaller
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
ms.openlocfilehash: ddea5a74dbd40d097398d04c0b2bc274df5ec972
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299997"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL und der freethreaded Marshaller

Der ATL-Assistent für einfache Objekte die Seite "Attribute" bietet eine Option, die Ihre Klasse die freethreaded Marshaller (FTM) aggregieren kann.

Der Assistent generiert Code zum Erstellen einer Instanz von FTM in `FinalConstruct` und gibt diese Instanz in `FinalRelease`. Ein COM_INTERFACE_ENTRY_AGGREGATE-Makro wird automatisch hinzugefügt, um sicherzustellen, dass die COM-Zuordnung `QueryInterface` Anforderungen für [IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal) werden von der freethreaded Marshaller behandelt.

FTM bietet direkten Zugriff auf Schnittstellen für das Objekt von jedem Thread im selben Prozess, apartmentübergreifende Aufrufe beschleunigen. Diese Option ist für Klassen vorgesehen, die sowohl das Threadingmodell zu verwenden.

Wenn Sie diese Option verwenden zu können, müssen Klassen Verantwortung für die Threadsicherheit ihrer Daten ausführen. Darüber hinaus müssen Objekte, die die freethreaded Marshaler aggregiert und Schnittstellenzeiger abgerufen, die von anderen Objekten verwenden müssen zusätzliche Schritte, stellen Sie sicher, dass die Schnittstellen ordnungsgemäß gemarshallt werden. In der Regel umfasst das Speichern von den Schnittstellenzeiger in der globalen Schnittstellentabelle (GIT) und die Zeiger aus der GIT jedes Mal, wenn er verwendet wird. ATL stellt die Klasse [CComGITPtr](../atl/reference/ccomgitptr-class.md) zur Verwendung gespeichert, in der GIT-Schnittstellenzeiger auf.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)<br/>
[CoCreateFreeThreadedMarshaler](/windows/desktop/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)<br/>
[IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal)<br/>
[Verwenden Sie die globale Schnittstellentabelle](/windows/desktop/com/when-to-use-the-global-interface-table)<br/>
[In-Process-Server, Threadingprobleme](/windows/desktop/com/in-process-server-threading-issues)
