---
title: "Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten"
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
  - "Dialogfeldsteuerelemente, Aufrufen"
  - "Dialogfelder, auf Steuerelemente zugreifen"
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der erste Ansatz zum Herstellen des typsicheren Zugriff auf Steuerelemente verwendet eine Inlinedatei Memberfunktion, um den Rückgabetyp von Memberfunktion Klassen `CWnd``GetDlgItem` in den entsprechenden C\+\+\-Steuerelementtyp, wie in diesem Beispiel dargestellt:  
  
 [!CODE [NVC_MFCControlLadenDialog#50](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#50)]  
  
 Sie können diese Memberfunktion dann verwenden, um auf das Steuerelement in einer typsicheren Art mit dem Code zuzugreifen, der ähnlich dem folgenden ist:  
  
 [!CODE [NVC_MFCControlLadenDialog#51](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#51)]  
  
## Siehe auch  
 [Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [Typsicherer Zugriff auf Steuerelemente mit Code\-Assistenten](../mfc/type-safe-access-to-controls-with-code-wizards.md)