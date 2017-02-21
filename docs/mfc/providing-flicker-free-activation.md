---
title: "Bereitstellen flimmerfreier Aktivierung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Aktivierung [C++], flimmerfrei"
  - "Flimmern, MFC-ActiveX-Steuerelemente"
  - "MFC ActiveX-Steuerelemente [C++], flimmerfrei"
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Bereitstellen flimmerfreier Aktivierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn das Steuerelement identisch in inaktiven und aktiven Zustände \(und verwendet nicht fensterlose Aktivierung\), sich zeichnet, können Sie die Zeichenvorgänge und das dazugehörige visuelle Flimmern beseitigen, die normalerweise vorkommen, wenn der Übergang zwischen den inaktiven und aktiven Zustände machen.  Hierzu, schließen Sie das Flag **noFlickerActivate** im Satz von Flags ein, die von [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) zurückgegeben werden.  Beispiel:  
  
 [!CODE [NVC_MFC_AxOpt#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#5)]  
[!CODE [NVC_MFC_AxOpt#13](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#13)]  
[!CODE [NVC_MFC_AxOpt#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#7)]  
  
 Der Code, mit dem dieses Flags einzuschließen wird automatisch generiert, wenn Sie die Option **Flimmerfreie Aktivierung** auf der Seite [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) auswählen, wenn Sie das Steuerelement mit dem MFC\-ActiveX\-Steuerelement\-Assistenten erstellen.  
  
 Wenn Sie fensterlose Aktivierung verwenden, verfügt diese Optimierung keine Auswirkungen.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)