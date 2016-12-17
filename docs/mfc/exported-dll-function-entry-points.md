---
title: "Einstiegspunkte f&#252;r exportierte DLL-Funktionen"
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
  - "DLLs exportieren, Funktionen"
  - "MFC, Verwalten der Zustandsdaten"
  - "Zustandsverwaltung, exportierte DLLs"
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Einstiegspunkte f&#252;r exportierte DLL-Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei exportierten Funktionen einer DLL, verwenden Sie das [korrekten](../Topic/AFX_MANAGE_STATE.md)\-Makro, um den ordnungsgemäßen globalen Zustand beim Wechsel vom beizubehalten DLL\-Modul der DLL der aufrufenden Anwendung.  
  
 Wenn sie aufgerufen wird, legt dieses Makro `pModuleState`, einen Zeiger auf eine `AFX_MODULE_STATE`\-Struktur fest, die globale Daten für das Modul, wenn der effektive Modulzustand für den Rest des enthaltenen Gültigkeitsbereich der Funktion enthält.  Nach dem Verlassen des Panels, das Makro enthalten, wird der vorherige effektive Modulzustand automatisch wiederhergestellt.  
  
 Diese Umschaltung wird erreicht, indem eine Instanz einer **AFX\_MODULE\_STATE** \-Klasse auf dem Stapel erstellt.  In seinem Konstruktor empfängt diese Klasse einen Zeiger auf den aktuellen Modulzustand und speichert ihn in der Membervariable und anschließend `pModuleState` als der neue effektive Modulzustand fest.  In ihrem Destruktor Diese Klasse stellt den Zeiger zurück, der in der Membervariable als der effektive Modulzustand gespeichert wird.  
  
 Wenn Sie eine exportierte Funktion haben, z eine, die ein Dialogfeld in der DLL wird, müssen Sie den folgenden Code am Anfang der Funktion hinzufügen:  
  
 [!CODE [NVC_MFCConnectionPoints#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCConnectionPoints#6)]  
  
 Dies tauscht den Modulzustand mit dem Zustand aus, der über [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md) auf das Ende des aktuellen Bereichs zurückgegeben wird.  
  
 Probleme mit Ressourcen in DLLs treten auf, wenn das Makro `AFX_MANAGE_STATE` nicht verwendet wird.  Standardmäßig verwendet MFC wie Ressourcenhandle der Hauptanwendung, die Ressourcenvorlage zu laden.  Diese Vorlage wird tatsächlich in der DLL gespeichert.  Die Ursache besteht darin, dass Modulzustandsinformationen MFC nicht durch das Makro `AFX_MANAGE_STATE` umgeschaltet wurden.  Das Ressourcenhandle wird von MFC Modulzustand wiederhergestellt.  Lässt das Umschalten nicht des Modulzustandes ein falsches Ressourcenhandle verwendet werden.  
  
 `AFX_MANAGE_STATE` muss nicht, in jede Funktion in der DLL abgelegt werden.  Beispielsweise kann `InitInstance` von den MFC\-Code in der Anwendung ohne `AFX_MANAGE_STATE`, da MFC automatisch den Modulzustand vor `InitInstance` und dann Schaltern es zurück bewegt, nachdem `InitInstance` zurückkehrt.  Das gilt für alle Meldungszuordnungshandler erfüllt.  Reguläre DLL belegt tatsächlich eine spezielle Vorlagenfensterprozedur, die automatisch den Modulzustand umschaltet, bevor eine Meldung weiterleitet.  
  
## Siehe auch  
 [Verwalten der Statusdaten von MFC\-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)