---
title: "Speicherverwaltung: Rahmenzuordnung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Erkennen von Speicherverlusten"
  - "Rahmenzuordnung"
  - "Framevariablen"
  - "Framevariablen, automatische Löschung von"
  - "Heapzuordnung, vs. Rahmenzuordnung"
  - "Speicherreservierung, Rahmen"
  - "Speicherverluste, Zuordnen von Objekten im Frame"
  - "Speicherverluste, Ermitteln"
  - "Speicherverluste, Rahmenzuordnung"
  - "Speicher, Erkennen von Verlusten"
  - "Speicher, Freigeben"
  - "Speicher, Freigeben"
  - "Gültigkeitsbereich, Framevariablen"
  - "Stapelrahmen"
  - "Variablen, Framevariablen"
ms.assetid: 945a211a-6f4f-4679-bb6a-b0f2a0d4a6c1
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Speicherverwaltung: Rahmenzuordnung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zuordnung in den Frames erhält seinen Namen vom "Stapelrahmen" installiert wird, wenn eine Funktion aufgerufen wird.  Der Stapelrahmen ist ein Speicherbereich, die vorübergehend die Argumente der Funktion enthält sowie weitere Variablen, die definierte lokale Variable der Funktion sind.  Feldvariablen werden häufig "auto" Variablen aufgerufen, da der Compiler automatisch den Speicherplatz für sie.  
  
 Es gibt zwei Schlüsseleigenschaften von Framezuordnungen.  Zuerst wenn Sie eine lokale Variable definieren, ist ausreichend Platz auf dem Stapelrahmen zugeordnet, um die gesamte Variable enthalten, selbst wenn ein großes Array oder eine Datenstruktur ist.  Zweitens Framevariablen werden automatisch deaktiviert, wenn sie den Gültigkeitsbereich verlassen:  
  
 [!CODE [NVC_MFC_Utilities#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#10)]  
  
 Für lokale Funktionsvariablen geschieht dieser Bereichsübergang, wenn die Funktion abgeschlossen, aber der Gültigkeitsbereich einer Framevariable kann als eine Funktion kleiner sein, wenn geschachtelte geschweifte Klammern verwendet werden.  Diese automatische Löschen von Framevariablen ist äußerst wichtig.  Bei der einfachen primitiven Typen \(wie `int` oder **byte**\), sind Arrays oder Datenstrukturen, das automatische Löschen einfach den Speicher frei, der von der Variablen verwendet wird.  Wenn die Variable den Gültigkeitsbereich erloschen ist, kann auf sie keine zur zugegriffen werden.  Bei C\+\+\-Objekte jedoch ist der Prozess des automatischen Löschens ein bisschen komplizierter.  
  
 Wenn ein Objekt als Framevariable definiert wird, wird der Konstruktor automatisch am Punkt aufgerufen, in dem die Definition erreicht wird.  Wenn das Objekt den Gültigkeitsbereich verlässt, wird ihr Destruktor automatisch aufgerufen, bevor der Speicher des Objekts freigegeben wird.  Diese automatische Erstellung und Zerstörung können sehr zweckmäßig, müssen Sie jedoch die automatische Aufrufe, insbesondere den Destruktor berücksichtigen.  
  
 Der Hauptvorteil beim Verknüpfen von Objekten über den Frame ist, dass es automatisch gelöscht werden.  Wenn Sie den Objekten über den Frame zuordnen, müssen Sie sich nicht um die vergessenen Objekte befürchten, die Speicherverluste verursachen. \(Ausführliche Informationen zu Speicherverlusten, finden Sie im Artikel [Erkennen von Speicherverlusten in MFC](assetId:///29ee8909-96e9-4246-9332-d3a8aa8d4658).\) Ein Nachteil der Framezuordnung ist, dass Framevariablen nicht außerhalb des Bereichs verwendet werden können.  Ein weiterer Faktor, wenn er Framezuordnung anhand Heapreservierung auswählt, ist der für große Strukturen und Objekte, ist es oft leichter, den Heap anstelle des Stapels zum Speichern zu verwenden, da Stapelspeicher oft eingeschränkt wird.  
  
## Siehe auch  
 [Speicherverwaltung](../mfc/memory-management.md)