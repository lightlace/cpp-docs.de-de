---
title: "Aktivierung (C++)"
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
  - "Aktivieren von Objekten"
  - "Aktivierung [C++]"
  - "Aktivierung [C++], Eingebettete OLE-Elemente"
  - "Dokumente, OLE"
  - "Eingebettete Objekte"
  - "Direkte Aktivierung"
  - "Direkte Aktivierung, Eingebettete und verknüpfte Ressourcen"
  - "OLE [C++], Aktivierung"
  - "OLE [C++], Bearbeiten"
  - "OLE [C++], Direkte Aktivierung"
  - "OLE-Aktivierung"
  - "OLE-Elemente, Visuelle Bearbeitung"
  - "OLE-Serveranwendungen, Aktivierung"
  - "Visuelle Bearbeitung"
  - "Visuelle Bearbeitung, Aktivierung"
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Aktivierung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die Rolle Aktivierung in der visuellen Bearbeitung OLE\-Elemente.  Nachdem ein Benutzer ein OLE\-Element in einem Containerdokument eingebettet wurden, muss möglicherweise verwendet werden.  Hierzu doppelklicken, der Benutzer auf das Element, das dieses Element aktiviert.  Die häufigste Aktivität zur Aktivierung bearbeitet.  Viele aktuelle OLE\-Elemente, wenn sie für Bearbeiten aktiviert werden, dass die Menüs und Symbolleisten im aktuellen Rahmenfenster der Änderung, die an, die der Anwendung gehören, die das Element erstellt wurde.  Dies Verhalten, bekannt als direkte Aktivierung, ermöglicht dem Benutzer, um jedes eingebettete Element in einem Verbunddokument bearbeiten, ohne das Fenster des Containerdokuments zu belassen.  
  
 Es ist auch möglich, eingebettete OLE\-Elemente in einem separaten Fenster zu bearbeiten.  Dies geschieht, wenn entweder der Container oder die Serveranwendung keine direkte Aktivierung unterstützt.  In diesem Fall der Benutzer auf ein eingebettetes Element doppelklicken, wird die Serveranwendung in einem separaten Fenster gestartet und das eingebettete Element erscheint als eigenes Dokument.  Der Benutzer bearbeitet das Element in diesem Fenster.  Wenn die Bearbeitung abgeschlossen ist, wird der Benutzer die Serveranwendung und kehrt zu der Containeranwendung zurück.  
  
 Alternativ kann der Benutzer "geöffnet Bearbeiten" mit dem Befehl **\<object\> Open** im Menü **Bearbeiten** auswählen.  Dadurch wird das Objekt in einem separaten Fenster.  
  
> [!NOTE]
>  Eingebettete Elemente in einem separaten Fenster bearbeiten war Standardverhalten in Version 1 von OLE, und einige OLE\-Anwendungen unterstützen möglicherweise nur dieses Format der Bearbeitung.  
  
 Direkte Aktivierung unterstützt einen dokumentorientierten Ansatz zur Dokumenterstellung höher.  Der Benutzer kann ein Verbunddokument als einzelne Entität behandeln und daran arbeiten, ohne zwischen Anwendungen zu wechseln.  wird jedoch direkte Aktivierung nur für eingebettete Elemente, nicht für verknüpfte Elemente verwendet: sich in einem separaten Fenster bearbeitet werden.  Dies ist, da ein verknüpftes Element tatsächlich an einer anderen Stelle gespeichert wird.  Die Bearbeitung ein verknüpftes Element wird innerhalb des tatsächlichen Kontext der Daten z. B. statt wo die Daten gespeichert werden.  Das Bearbeiten eines verknüpften Elements in einem separaten Fenster erinnert den Benutzer, dass die Daten einem anderen Dokument gehören.  
  
 MFC unterstützt keine geschachtelten direkte Aktivierung.  Wenn Sie eine bin\/Server\-Anwendung erstellen und diesen Container\/Server in einem anderen Container und direkten in aktiviert eingebettet wird, kann er direkt die Objekte nicht aktivieren, die darauf eingebettet werden.  
  
 Was in einem eingebetteten Element eintritt, wenn der Benutzerdoppelklicke ist von Verben abhängt, die für das Element definiert werden.  Weitere Informationen finden Sie unter [Aktivierung: Verben](../mfc/activation-verbs.md).  
  
## Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [Container](../mfc/containers.md)   
 [Server](../mfc/servers.md)