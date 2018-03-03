---
title: 'Speicherverwaltung: Frame-Zuordnung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- memory leaks [MFC], frame allocation
- memory [MFC], detecting leaks
- memory [MFC], reclaiming
- memory allocation [MFC], frames
- frame variables [MFC], automatic deletion of
- scope [MFC], frame variables
- heap allocation [MFC], vs. frame allocation
- variables [MFC], frame variables
- memory leaks [MFC], detecting
- memory, releasing [MFC]
- stack frames [MFC]
- memory leaks [MFC], allocating objects on the frame
- detecting memory leaks [MFC]
- frame allocation [MFC]
- frame variables [MFC]
ms.assetid: 945a211a-6f4f-4679-bb6a-b0f2a0d4a6c1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 03a8e5f81e55398ffba30479ecfafc42726e9519
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-frame-allocation"></a>Speicherverwaltung: Rahmenzuordnung
Zuordnung für den Frame nimmt seinen Namen aus der "Stapelrahmen", die festgelegt wird nach oben, wenn eine Funktion aufgerufen wird. Die Stack-Frame ist ein Bereich des Arbeitsspeichers, der vorübergehend die Argumente der Funktion sowie alle Variablen, die definiert enthält, werden in der Funktion lokal. Framevariablen werden häufig "Automatische" Variablen bezeichnet, da der Compiler automatisch die Speicherplatz für sie reserviert.  
  
 Es gibt zwei wichtige Merkmale der Frame-Zuordnungen. Zuerst beim Definieren einer lokalen Variablen ist genügend Speicherplatz auf den Stapelrahmen, um die gesamte Variable speichern zugeordnet, selbst wenn es sich um ein großes Array oder eine Datenstruktur handelt. Zweitens Framevariablen werden automatisch gelöscht, wenn sie den Gültigkeitsbereich verlassen:  
  
 [!code-cpp[NVC_MFC_Utilities#10](../mfc/codesnippet/cpp/memory-management-frame-allocation_1.cpp)]  
  
 Für lokale Variablen erfolgt dieser Übergang Bereich auf, wenn die Funktion beendet wird, aber der Gültigkeitsbereich einer Variablen Frame kleiner als eine Funktion werden können, wenn geschachtelte geschweifter Klammern verwendet werden. Diese automatische Löschen von Framevariablen ist sehr wichtig. Bei einfacher, primitiver Typen (z. B. `int` oder **Byte**), Arrays oder Datenstrukturen, das automatische Löschen gibt einfach den Arbeitsspeicher, die durch die Variable verwendet. Da die Variable den Gültigkeitsbereich verlassen hat, kann es dennoch zugegriffen werden. Im Fall von C++-Objekte versteht man jedoch Automatisches Löschen etwas komplizierter.  
  
 Wenn ein Objekt als Framevariable definiert ist, wird dessen Konstruktor automatisch an dem Punkt aufgerufen, in dem die Definition gefunden wird. Wenn das Objekt den Gültigkeitsbereich verlässt, wird der Destruktor automatisch aufgerufen, bevor der Speicher für das Objekt freigegeben wird. Diese automatische Konstruktion und Zerstörung können sehr nützlich sein müssen, jedoch Sie beachten Sie die automatische Aufrufe, insbesondere den Destruktor.  
  
 Der Hauptvorteil bei der Zuweisung von Objekten im Frame ist, dass sie automatisch gelöscht werden. Wenn Sie Ihre Objekte auf den Frame zuordnen, müssen Sie kümmern vergessenes Objekte, die Speicherverluste verursachen. (Ausführliche Informationen zu Speicherverlusten, finden Sie im Artikel [feststellen von Speicherverlusten in MFC](http://msdn.microsoft.com/en-us/29ee8909-96e9-4246-9332-d3a8aa8d4658).) Ein Nachteil von rahmenzuordnung ist Framevariablen außerhalb ihres Bereichs verwendet werden können. Ein weiterer Faktor bei der Wahl rahmenzuordnung im Vergleich zu Heapzuordnung besteht darin, dass für große Strukturen und Objekte, oft besser, die den Heap anstatt des Stapels für die Speicherung verwenden, da Stapelspeicher häufig beschränkt ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherverwaltung](../mfc/memory-management.md)

