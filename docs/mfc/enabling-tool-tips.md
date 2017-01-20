---
title: "Erstellen von QuickInfos"
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
  - "Erstellen von QuickInfos"
  - "Initialisieren QuickInfos"
  - "QuickInfos [C++], Aktivieren"
  - "QuickInfos [C++], Initialisieren"
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen von QuickInfos
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können QuickInfounterstützung für die untergeordneten Steuerelemente eines Fensters ermöglichen \(z die Steuerelemente auf einer Formularansicht oder Dialogfeld\).  
  
### So QuickInfo für die untergeordneten Steuerelemente eines Fensters ermöglichen  
  
1.  Rufen Sie `EnableToolTips` für das Fenster auf, für das Sie QuickInfos bereitstellen möchten.  
  
2.  Erstellen Sie eine Zeichenfolge für jedes Steuerelement im [TTN\_NEEDTEXT\-Benachrichtigung](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)\-Handler bereit.  Der Handler wird in der Meldungszuordnung des Fensters, das die untergeordneten Steuerelemente enthält \(beispielsweise, die Formularansichtsklasse\).  Dieser Handler sollte eine Funktion aufrufen, die das Steuerelement identifiziert und **pszText** festgelegt, um den Text anzugeben, der durch das ToolTip\-Steuerelement verwendet wird.  
  
## Siehe auch  
 [QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)