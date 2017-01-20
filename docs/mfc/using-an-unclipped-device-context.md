---
title: "Verwenden eines Ger&#228;tekontexts ohne Clippingbereichsanpassung"
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
  - "MFC-ActiveX-Steuerelemente, Ungeschnittener Gerätekontext"
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden eines Ger&#228;tekontexts ohne Clippingbereichsanpassung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie System.EventArgs, dass das Steuerelement nicht außerhalb des Clientrechtecks zeichnet, können Sie einen kleinen jedoch auffindbaren Geschwindigkeitsgewinn erkennen, indem Sie den Aufruf `IntersectClipRect` deaktivieren, der durch `COleControl` ausgeführt werden.  Hierzu, entfernen Sie das Flag **clipPaintDC** aus dem Satz von Flags, die von [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) zurückgegeben werden.  Beispiel:  
  
 [!CODE [NVC_MFC_AxOpt#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#5)]  
[!CODE [NVC_MFC_AxOpt#14](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#14)]  
[!CODE [NVC_MFC_AxOpt#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#7)]  
  
 Der Code, mit dem dieses Flags entfernen wird automatisch generiert, wenn Sie die Option **Nicht\-geschnittener Gerätekontext** auf der Seite [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) auswählen, wenn das Steuerelement mit dem MFC\-ActiveX\-Steuerelement\-Assistenten erstellt wird.  
  
 Wenn Sie fensterlose Aktivierung verwenden, verfügt diese Optimierung keine Auswirkungen.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)