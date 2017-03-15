---
title: "Implementation of a Custom String Manager (Advanced Method) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlStringMgr class, Verwenden"
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Implementation of a Custom String Manager (Advanced Method)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In besonderen Fällen sollten Sie einen benutzerdefinierten Zeichenfolgenmanager implementieren, der mehr als nur Änderung bewirkt, die Heap verwendet wird, um Speicher reserviert.  In diesem Fall müssen Sie die [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md)\-Schnittstelle als der benutzerdefinierte Zeichenfolgenmanager manuell implementieren.  
  
 Um dies zu erreichen, ist es wichtig zu zuerst versteht wie [CStringT](../atl-mfc-shared/reference/cstringt-class.md) verwendet die herstellen um die Zeichenfolgendaten zu verwalten.  Jede Instanz von `CStringT` verfügt über einen Zeiger auf eine Struktur [CStringData](../atl-mfc-shared/reference/cstringdata-class.md).  Diese Struktur mit variabler Länge enthält wichtige Informationen über die Zeichenfolge \(wie Länge\) sowie die tatsächlichen Textdaten für die Zeichenfolge.  Jeder benutzerdefinierte Zeichenfolgenmanager ist zum Belegen und Freigeben dieser Strukturen auf Anforderung von `CStringT` zuständig.  
  
 Die `CStringData`\-Struktur enthält vier Felder:  
  
-   [pStringMgr](../Topic/CStringData::pStringMgr.md) dieses Feld zeigt auf die `IAtlStringMgr`\-Schnittstelle, die verwendet wird, um die Zeichenfolgendaten zu verwalten.  Wenn `CStringT` Anforderungen, den Zeichenfolgenpuffer neu belegen oder freizugeben es die Neuzuteilung aufruft oder die Methoden dieser Schnittstelle freigibt und übergibt die `CStringData`\-Struktur als Parameter.  Wenn Sie eine `CStringData`\-Struktur im Zeichenfolgenmanager zuordnen, muss dieses Feld festlegen, damit sie auf dem benutzerdefinierten Zeichenfolgenmanager zeigen.  
  
-   [nDataLength](../Topic/CStringData::nDataLength.md) dieses Feld enthält die aktuelle logische Länge der Zeichenfolge, die im Puffer ausschließlich des abschließenden NULL\-Zeichens gespeichert wird.  `CStringT` aktualisiert dieses Feld, wenn die Länge der Zeichenfolge geändert.  Wenn eine `CStringData`\-Struktur zugeordnet ist, muss das Zeichenfolgenmanager dieses Feld auf Null.  Wenn eine `CStringData`\-Struktur zuordnet, muss der benutzerdefinierte Zeichenfolgenmanager dieses Feld unverändert beibehalten.  
  
-   [nAllocLength](../Topic/CStringData::nAllocLength.md) dieses Feld enthält die maximale Anzahl von Zeichen \(ohne des abschließenden NULL\-Zeichens\) die in diesem Zeichenfolgenpuffer gespeichert werden können, ohne sie neu belegen.  Sobald `CStringT` Anforderungen, die logische Länge der Zeichenfolge zu erhöhen, es zuerst dieses Feld überprüft, um sicherzustellen, dass genügend Speicherplatz im Puffer.  Wenn die Überprüfung fehlschlägt, `CStringT` Aufrufe in den benutzerdefinierten Zeichenfolgenmanager, um des Puffers neu belegen.  Wenn das Zuordnen oder die Neuzuteilung einer `CStringData`\-Struktur, Sie dieses Feld die Anzahl von Zeichen mindestens festlegen müssen, die im **nChars**\-Parameter zu [IAtlStringMgr::Allocate](../Topic/IAtlStringMgr::Allocate.md) oder zu [IAtlStringMgr::Reallocate](../Topic/IAtlStringMgr::Reallocate.md) angefordert werden.  Wenn es mehr Platz im Puffer als angefordert wird, können Sie diesen Wert festlegen, um den tatsächlichen verfügbaren Platz zu entsprechen.  Dadurch können `CStringT`, um die Zeichenfolge zu erweitern, um den gesamten zugeordneten Platz auszufüllen, bevor sie zurück in den Zeichenfolgenmanager aufrufen muss, um den Puffer neu belegen.  
  
-   [nRefs](../Topic/CStringData::nRefs.md) dieses Feld enthält den Verweiszähler des aktuellen Zeichenfolgenpuffers.  Ist der Wert von ist, dann verwendet eine einzelne Instanz von `CStringT` den Puffer.  Außerdem wird die Instanz zu gelesen zulässt und den Inhalt des Puffers ändert.  Wenn der Wert größer als einer ist, können mehrere Instanzen von `CStringT` den Puffer verwenden.  Da der Zeichenpuffer freigegeben wird, können `CStringT`\-Instanzen den Inhalt des Puffers nur lesen.  Um den Inhalt zu ändern, erstellt `CStringT` zuerst eine Kopie aus dem Puffer.  Wenn der Wert negativ ist, nur eine Instanz von `CStringT` den Puffer verwendet.  In diesem Fall gilt der Puffer als gesperrt.  Wenn eine `CStringT`\-Instanz einen gesperrten keinen Puffer verwendet, können andere Instanzen von `CStringT` den Puffer frei.  Stattdessen erstellen diese Instanzen eine Kopie des Puffers, bevor sie den Inhalt bearbeiten.  Außerdem versucht die `CStringT`\-Instanz mithilfe des gesperrten Puffers nicht, den Puffer einer anderen Instanz `CStringT` freizugeben, die an sie zugewiesen wird.  In diesem Fall kopiert die `CStringT`\-Instanz die andere Zeichenfolge in den gesperrten Puffer.  
  
     Wenn Sie eine `CStringData`\-Struktur zuordnen, muss dieses Feld festlegen, um den Typ der Freigabe widerzuspiegeln, der für den Puffer zulässig ist.  Für die meisten Implementierungen legen Sie diesen Wert auf einen fest.  Dadurch können übliche Kopie\-aufWRITE, das Verhalten freigibt.  Wenn das Zeichenfolgenmanager nicht das Freigeben des Zeichenfolgenpuffers unterstützt, legen Sie dieses Feld in ein gesperrtes Zustand.  Dadurch wird `CStringT`, um diesen Puffer für die Instanz von `CStringT` nur zu verwenden, die ihn zugeordnet sind.  
  
## Siehe auch  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)