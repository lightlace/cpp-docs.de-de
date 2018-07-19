---
title: Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (Methode "Erweitert") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d72ce586c7c93f6bd5ade613ab2807398a13ab7
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882155"
---
# <a name="implementation-of-a-custom-string-manager-advanced-method"></a>Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (fortgeschrittene Methode)
In speziellen Fällen empfiehlt es sich um eines benutzerdefinierten zeichenfolgenmanagers zu implementieren, das mehr als nur ändert der Heap verwendet wird, um Speicher zu belegen. In diesem Fall müssen Sie manuell implementieren die [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) Schnittstelle als benutzerdefinierte Zeichenfolge-Manager.  
  
 Zu diesem Zweck es ist wichtig, zunächst verstehen, wie [CStringT](../atl-mfc-shared/reference/cstringt-class.md) verwendet die Schnittstelle, um die Zeichenfolgendaten zu verwalten. Jede Instanz des `CStringT` verfügt über einen Zeiger auf eine [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) Struktur. Diese Struktur variabler Länge enthält wichtige Informationen über die Zeichenfolge (z. B. Länge), sowie die Zeichen tatsächlich Daten für die Zeichenfolge an. Alle benutzerdefinierten zeichenfolgenmanagers ist verantwortlich für das zuordnen und Freigeben von diesen Strukturen auf Anforderung des `CStringT`.  
  
 Die `CStringData` Struktur besteht aus vier Felder:  
  
-   [pStringMgr](../atl-mfc-shared/reference/cstringdata-class.md#pstringmgr) dieses Feld zeigt die `IAtlStringMgr` verwendete Schnittstelle zum Verwalten von Zeichenfolgen. Wenn `CStringT` muss neu zuordnen oder Freigeben des Zeichenfolgenpuffers Ruft die erneut oder die kostenlose Methoden dieser Schnittstelle, übergeben die `CStringData` Struktur als Parameter. Beim Zuweisen einer `CStringData` Struktur in der Zeichenfolgen-Manager, müssen Sie dieses Feld, um auf Ihre benutzerdefinierten zeichenfolgenmanagers verweisen festlegen.  
  
-   [nDataLength](../atl-mfc-shared/reference/cstringdata-class.md#ndatalength) dieses Feld enthält die aktuelle logische Länge der Zeichenfolge im Puffer, ohne das abschließende Nullzeichen gespeichert. `CStringT` Dieses Feld wird aktualisiert, wenn die Länge der Zeichenfolge ändert. Beim Zuweisen einer `CStringData` Struktur der Zeichenfolgen-Manager muss dieses Feld auf 0 festgelegt. Beim Neuzuordnen von einem `CStringData` Struktur Ihrer benutzerdefinierten zeichenfolgenmanagers muss dieses Feld unverändert lassen.  
  
-   [nAllocLength](../atl-mfc-shared/reference/cstringdata-class.md#nalloclength) dieses Feld enthält die maximale Anzahl von Zeichen, die in diesem Zeichenfolgenpuffer gespeichert werden können, ohne es erneut zugewiesen werden, die (ohne das abschließende Nullzeichen). Wenn `CStringT` erhöhen Sie die logische Länge der Zeichenfolge ist, muss zuerst wird geprüft, dieses Feld, um sicherzustellen, dass genügend Speicherplatz im Puffer vorhanden ist. Wenn die Überprüfung fehlschlägt, `CStringT` Aufrufe in Ihrem benutzerdefinierten zeichenfolgenmanagers Puffer zu nutzen. Beim Zuweisen oder erneut zugewiesen werden, eine `CStringData` Struktur die, Sie müssen festgelegt werden, Feld um mindestens die Anzahl der Zeichen, die im angeforderten der *nChars* Parameter [IAtlStringMgr::Allocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#allocate) oder [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate). Wenn mehr Speicherplatz in den Puffer als angeforderten vorhanden ist, können Sie diesen Wert entsprechend der tatsächlichen Menge des verfügbaren Speicherplatzes festlegen. Dadurch können `CStringT` vergrößert die Zeichenfolge, um die gesamte füllen reservierte Speicherplatz muss einen Rückruf in den Zeichenfolgen-Manager den Puffer zu nutzen.  
  
-   [nRefs](../atl-mfc-shared/reference/cstringdata-class.md#nrefs) dieses Feld enthält die aktuelle Verweisanzahl des Zeichenfolgenpuffers. Wenn der Wert anschließend hat eine einzelne Instanz `CStringT` wird mithilfe des Puffers. Darüber hinaus kann die Instanz zu lesen und ändern Sie den Inhalt des Puffers. Wenn der Wert größer als eins, mehrere Instanzen von `CStringT` können Sie den Puffer. Da die Zeichenpuffer freigegeben werden, `CStringT` Instanzen können nur den Inhalt des Puffers lesen. So ändern Sie den Inhalt der `CStringT` zunächst eine Kopie des Puffers. Wenn der Wert negativ ist, wird nur eine Instanz des `CStringT` wird mithilfe des Puffers. In diesem Fall gilt der Puffer gesperrt. Wenn eine `CStringT` Instanz wird mithilfe eines gesperrten Puffers keine andere Instanzen von `CStringT` kann den Puffer freigeben. Diese Instanzen erstellen Sie eine Kopie des Puffers stattdessen vor dem Bearbeiten des Inhalts. Darüber hinaus die `CStringT` Instanz mit den gesperrten Puffer wird nicht versucht, den Puffer mit anderen Teilen `CStringT` Instanz zugewiesen ist. In diesem Fall die `CStringT` Instanz kopiert die andere Zeichenfolge in den Puffer gesperrt.  
  
     Beim Zuweisen einer `CStringData` Struktur, müssen Sie dieses Feld entsprechend den Typ der Freigabe, die für den Puffer darf festlegen. Legen Sie für die meisten Implementierungen diesen Wert auf einen. Dadurch wird das übliche Kopie-bei-Schreibvorgang-Freigabe-Verhalten. Wenn der Zeichenfolgen-Manager die gemeinsame Nutzung des Zeichenfolgenpuffers nicht unterstützt wird, legen Sie dieses Feld, zu sperren. Dies zwingt `CStringT` nur mit diesen Puffer für die Instanz von `CStringT` , die ihn zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung mit CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)

