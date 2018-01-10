---
title: Implementierung eines benutzerdefinierten Zeichenfolge-Managers (Methode erweitert) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: IAtlStringMgr class, using
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7e76edc65e5f30fee90f346d5434ecbee320a37a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementation-of-a-custom-string-manager-advanced-method"></a>Implementierung eines benutzerdefinierten Zeichenfolge-Managers (Erweiterte Methode)
In speziellen Fällen empfiehlt es sich möglicherweise so implementieren Sie einen benutzerdefinierte Zeichenfolge-Manager, der mehr als nur ändert die Heaps belegen von Speicher verwendet wird. In diesem Fall müssen Sie manuell implementieren die [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) Schnittstelle als benutzerdefinierte Zeichenfolge-Manager.  
  
 Zu diesem Zweck, es ist wichtig, zunächst verstehen, wie [CStringT](../atl-mfc-shared/reference/cstringt-class.md) verwendet diese Schnittstelle zum Verwalten von Zeichenfolgendaten. Jede Instanz des `CStringT` verfügt über einen Zeiger auf eine [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) Struktur. Diese Struktur variabler Länge enthält wichtige Informationen über die Zeichenfolge (z. B. Länge), sowie die tatsächliche Zeichendaten für die Zeichenfolge an. Jede benutzerdefinierte Zeichenfolge ist verantwortlich für das zuordnen und Freigeben von diesen Strukturen auf Anforderung des `CStringT`.  
  
 Die `CStringData` Struktur umfasst vier Felder:  
  
-   [pStringMgr](../atl-mfc-shared/reference/cstringdata-class.md#pstringmgr) dieses Feld zeigt die `IAtlStringMgr` Schnittstelle zum Verwalten von Zeichenfolgendaten verwendet. Wenn `CStringT` muss zuordnen oder Freigeben des Zeichenfolgenpuffers aufgerufen wird, werden die neu zuordnen oder freien Methoden dieser Schnittstelle, übergeben die `CStringData` Struktur als Parameter. Beim Zuordnen einer `CStringData` Struktur in der Zeichenfolge-Managers müssen Sie dieses Feld, zeigen Sie auf Ihre benutzerdefinierte Zeichenfolge-Manager festlegen.  
  
-   [nDataLength](../atl-mfc-shared/reference/cstringdata-class.md#ndatalength) dieses Feld enthält die aktuelle logische Länge der Zeichenfolge im Puffer, ohne das abschließende Nullzeichen gespeichert. `CStringT`Dieses Feld wird aktualisiert, wenn die Länge der Zeichenfolge geändert wird. Beim Zuordnen einer `CStringData` -Struktur, die Zeichenfolgen-Manager muss dieses Feld auf 0 festgelegt. Bei der neuzuweisung eine `CStringData` -Struktur, Ihr benutzerdefinierter Zeichenfolgen-Manager muss lassen Sie dieses Feld nicht geändert.  
  
-   [nAllocLength](../atl-mfc-shared/reference/cstringdata-class.md#nalloclength) dieses Feld enthält die maximale Anzahl von Zeichen enthalten (ohne das abschließende Null-Zeichen), die in diesem Zeichenfolgenpuffer gespeichert werden können, ohne. Wenn `CStringT` erhöhen Sie die logische Länge der Zeichenfolge ist, muss dieses Feld, um sicherzustellen, dass genügend Speicherplatz vorhanden ist, im Puffer prüft zunächst. Wenn die Überprüfung fehlschlägt, `CStringT` Aufrufe in Ihrem benutzerdefinierten Zeichenfolgen-Manager weisen den Puffer. Beim Zuordnen von oder erneut zugewiesen werden, eine `CStringData` -Struktur, Sie müssen festlegen, Feld um mindestens die Anzahl der Zeichen, die im angeforderten der **nChars** Parameter [IAtlStringMgr::Allocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#allocate) oder [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate). Wenn Sie mehr Platz im Puffer als angeforderten vorhanden ist, können Sie diesen Wert entsprechend der tatsächlichen Menge des verfügbaren Speicherplatzes festlegen. Dadurch können `CStringT` vergrößert die Zeichenfolge, die gesamte zugewiesener Speicherplatz, bevor er wieder in der Zeichenfolge-Manager weisen den Puffer aufgerufen hat.  
  
-   [nRefs](../atl-mfc-shared/reference/cstringdata-class.md#nrefs) dieses Feld enthält die aktuelle Verweisanzahl des Zeichenfolgenpuffers. Wenn der Wert eine, und klicken Sie dann eine einzelne Instanz `CStringT` wird mithilfe des Puffers. Darüber hinaus kann die Instanz zu lesen und ändern Sie den Inhalt des Puffers. Wenn der Wert größer als 1 ist mehrere Instanzen von `CStringT` Puffer verwenden können. Da der Zeichenpuffer freigegeben werden, `CStringT` Instanzen können nur den Inhalt des Puffers lesen. Zum Ändern des Inhalts `CStringT` erstellt zunächst eine Kopie des Puffers. Wenn der Wert negativ ist, wird nur eine Instanz des `CStringT` wird mithilfe des Puffers. In diesem Fall gilt der Puffer gesperrt. Wenn eine `CStringT` Instanz wird unter Verwendung eines gesperrten Puffers keine weiteren Instanzen `CStringT` Puffer freigeben kann. Diese Instanzen erstellen Sie eine Kopie des Puffers stattdessen vor Manipulation der Inhalte. Darüber hinaus die `CStringT` -Instanz unter Verwendung des gesperrten Puffers versucht nicht, den Puffer eines anderen freigeben `CStringT` Instanz zugewiesen. In diesem Fall die `CStringT` Instanz kopiert die andere Zeichenfolge in den Puffer gesperrt.  
  
     Beim Zuordnen einer `CStringData` Struktur, müssen Sie dieses Feld, um den Typ der Freigabe widerspiegelt, die für den Puffer darf festlegen. Legen Sie für die meisten Implementierungen dieser Wert auf eine. Dadurch wird das übliche Freigabe Kopie-bei-Schreibvorgang-Verhalten. Wenn der Zeichenfolgen-Manager die gemeinsame Nutzung des Zeichenfolgenpuffers unterstützt, legen Sie dieses Feld, in einem gesperrten Zustand. Dies zwingt `CStringT` auf die Verwendung dieses Puffers für die Instanz von `CStringT` , die zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung mit CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)

