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
ms.openlocfilehash: 94e4961c69e9441d160d72d9b72afcee3677e25f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491911"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL und der freethreaded Marshaller

Die Seite Attribute des ATL-Assistenten für einfache Objekte enthält eine Option, mit der Ihre Klasse den Free Threaded Mars Haller (FTM) aggregieren kann.

Der Assistent generiert Code, um eine Instanz des frei Hand Thread-Mars Haller in `FinalConstruct` zu erstellen und diese Instanz `FinalRelease`in freizugeben. Der com-Zuordnung wird automatisch ein COM_INTERFACE_ENTRY_AGGREGATE-Makro hinzugefügt, `QueryInterface` um sicherzustellen, dass Anforderungen für [IMarshal](/windows/win32/api/objidlbase/nn-objidlbase-imarshal) vom Free Threaded-Mars Haller verarbeitet werden.

Der frei Thread-Mars Haller ermöglicht den direkten Zugriff auf Schnittstellen auf Ihrem Objekt von einem beliebigen Thread im gleichen Prozess und beschleunigt die übergreifenden Aufrufe. Diese Option ist für Klassen vorgesehen, die das beide Threading Modell verwenden.

Wenn diese Option verwendet wird, müssen Klassen die Verantwortung für die Thread Sicherheit Ihrer Daten übernehmen. Außerdem müssen Objekte, die den freien Thread-Mars Haller aggregieren und Schnittstellen Zeiger verwenden müssen, die von anderen Objekten abgerufen werden, zusätzliche Schritte ausführen, um sicherzustellen, dass die Schnittstellen ordnungsgemäß gemarshallt werden. In der Regel umfasst dies das Speichern der Schnittstellen Zeiger in der globalen Schnittstellen Tabelle (Global Interface Table, git) und das erhalten des Zeigers aus dem git bei jeder Verwendung. ATL stellt die [CComGITPtr](../atl/reference/ccomgitptr-class.md) -Klasse bereit, um Sie bei der Verwendung von im git gespeicherten Schnittstellen Zeigern zu unterstützen.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)<br/>
[CoCreateFreeThreadedMarshaler](/windows/win32/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)<br/>
[Von IMarshal](/windows/win32/api/objidlbase/nn-objidlbase-imarshal)<br/>
[Verwendungszwecke der globalen Schnittstellen Tabelle](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[Threading Probleme im Prozess internen Server](/windows/win32/com/in-process-server-threading-issues)
