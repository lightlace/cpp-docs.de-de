---
title: "Deaktivieren der Option „Aktiviert, wenn sichtbar“"
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
  - "MFC-ActiveX-Steuerelemente [C++], Optionen zur Aktivierung"
  - "Aktiv wenn sichtbar-Option"
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Deaktivieren der Option „Aktiviert, wenn sichtbar“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Steuerelement verfügt über zwei grundlegende Zustände: aktiv und inaktiv.  In der Vergangenheit unterschieden sich diese Zustände dadurch, ob das Steuerelement ein Fenster hatte oder nicht.  Ein aktives Steuerelement wies ein Fenster auf, ein inaktives Steuerelement wies kein Fenster auf.  Mit der Einführung der fensterlose Aktivierung, ist diese Unterscheidung nicht mehr universell, gilt aber weiterhin für viele Steuerelemente.  
  
 Verglichen mit der Initialisierung, die üblicherweise von ein ActiveX\-Steuerelement ausgeführt wird, wird die Erstellung eines Fensters ein sehr viel Rechenleistung.  Idealerweise hätte ein Steuerelement das Erstellen des Fensters bis absolut notwendig ausgecheckt verzögern.  
  
 Viele Steuerelemente, müssen nicht aktiv festlegen die Gesamtzeit, die in einem Container sichtbar sind.  Häufig kann ein Steuerelement in inaktiven Zustand verbleiben, bis der Benutzer einen Vorgang ausführt, die es benötigt, aktiv werden, \(beispielsweise Klicken mit der Maus oder Die TAB\-TASTE drücken\).  Um ein Steuerelement zu bewirken auf den Container zu inaktiv bleiben muss sie aktivieren, entfernen das Flag **OLEMISC\_ACTIVATEWHENVISIBLE** aus verschiedenen Flags des Steuerelements:  
  
 [!CODE [NVC_MFC_AxOpt#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#9)]  
  
 Das **OLEMISC\_ACTIVATEWHENVISIBLE**\-Flag wird automatisch weggelassen, wenn Sie die Option **Aktivieren, wenn sichtbar** in der [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite MFC\-ActiveX\-Steuerelement\-Assistenten deaktivieren, wenn Sie das Steuerelement erstellt.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)