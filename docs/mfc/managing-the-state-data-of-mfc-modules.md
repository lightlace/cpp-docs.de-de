---
title: "Verwalten der Statusdaten von MFC-Modulen"
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
  - "Datenverwaltung [C++]"
  - "Datenverwaltung [C++], MFC-Module"
  - "Exportierte Schnittstellen und globaler Zustand [C++]"
  - "Globaler Zustand [C++]"
  - "MFC [C++], Verwalten der Zustandsdaten"
  - "Modulzustand wiederhergestellt"
  - "Modulzustände, Speichern und Wiederherstellen"
  - "Mehrfachmodule"
  - "Einstiegspunkte für Fensterprozeduren [C++]"
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Verwalten der Statusdaten von MFC-Modulen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel werden die Zustandsdaten von MFC\-Modulen und wie dieser Zustand aktualisiert wird, wenn der Fluss der Ausführung \(der Pfadcode akzeptiert von einer Anwendung der Ausführung\), Modul\- eingibt und verlässt.  Schaltmodulzustände mit den Makros `AFX_MANAGE_STATE` und `METHOD_PROLOGUE` wird auch erläutert.  
  
> [!NOTE]
>  Der Begriff "Modul" verweist hier ein ausführbares Programm oder eine DLL an \(oder auf den Satz DLLs\) das unabhängig vom Rest der Anwendung arbeiten, verwendet jedoch eine freigegebene Kopie der MFC\-DLL.  Ein ActiveX\-Steuerelement ist ein typisches Beispiel eines Moduls.  
  
 Wie in der folgenden Abbildung gezeigt wurde MFC Zustandsdaten für jedes Modul, das in einer Anwendung verwendet wird.  Beispiele für diese Daten enthalten Windows\-Instanzhandles \(zum Laden von Ressourcen\), Zeiger zu aktuellen `CWinApp` und den `CWinThread`\-Objekten einer Anwendung, OLE\-Modulverweiszähler und eine Vielzahl von Zuordnungen, die die Verbindung zwischen Windows\-Objekthandles und entsprechenden Instanzen von MFC\-Objekten beibehalten.  Wenn eine Anwendung über mehrere Module verwendet wird, gelten die Zustandsdaten jedes Moduls Anwendung nicht breit.  Stattdessen hat jedes Modul eigene Kopie der Zustandsdaten des MFC.  
  
 ![Zustandsdaten eines Einzelmoduls &#40;Anwendung&#41;](../mfc/media/vc387n1.png "vc387N1")  
Zustandsdaten eines Einzelmoduls \(Anwendung\)  
  
 Die Zustandsdaten eines Moduls werden in einer Struktur enthaltenen und sind stets über einen Zeiger auf diese Struktur verfügbar.  Wenn der den Ausführungsablauf ein bestimmtes Modul, wie in der folgenden Abbildung zeigt, die der Zustand des Moduls befinden muss der "aktuelle" oder "effektiver" Zustand.  Daher verfügt jedes Threadobjekt einen Zeiger an effektiven Staatsaufbau dieser Anwendung.  Diesen Zeiger zu halten Zeitpunkt aktualisiert ist zum Verwalten des globalen Zustand der Anwendung und das Beibehalten der Integrität dem Zustand jedes Moduls wichtig.  Falsche Verwaltung des globalen Zustand kann zu unvorhersehbarem Verhalten führen.  
  
 ![Zustandsdaten mehrerer Module](../mfc/media/vc387n2.png "vc387N2")  
Zustandsdaten mehrerer Module  
  
 Das bedeutet, dass jedes Modul für Modulzuständen an allen zwischen die Einstiegspunkte ordnungsgemäß wechseln zuständig.  Ein "Einstiegspunkt" ist jeder Stelle, in dem den Ausführungsablauf den Code des Moduls eingeben kann.  Einstiegspunkteinschließung:  
  
-   [Exportierte Funktionen in einer DLL](../mfc/exported-dll-function-entry-points.md)  
  
-   [Memberfunktionen von COM\-Schnittstellen](../mfc/com-interface-entry-points.md)  
  
-   [Fensterprozeduren](../mfc/window-procedure-entry-points.md)  
  
## Siehe auch  
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)