---
title: "Behandeln der TTN_NEEDTEXT-Benachrichtigung f&#252;r QuickInfos | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TTN_NEEDTEXT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benachrichtigungen, QuickInfos"
  - "QuickInfos [C++], Benachrichtigungen"
  - "TTN_NEEDTEXT-Meldung"
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Behandeln der TTN_NEEDTEXT-Benachrichtigung f&#252;r QuickInfos
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Als Teil [Aktivieren von QuickInfos](../mfc/enabling-tool-tips.md) bearbeiten Sie die **TTN\_NEEDTEXT** Meldung, indem Sie den folgenden Eintrag zur Meldungszuordnung des Besitzerfensters hinzufügen:  
  
 [!CODE [NVC_MFCControlLadenDialog#40](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#40)]  
  
 `memberFxn`  
 Die Memberfunktion, aufgerufen werden, wenn Text für diese Schaltfläche benötigt wird.  
  
 Beachten Sie, dass die ID einer QuickInfo immer 0.  
  
 Deklarieren Sie die Handlerfunktion in der Klassendefinition, wie folgt:  
  
 [!CODE [NVC_MFCControlLadenDialog#53](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#53)]  
  
 wobei die kursiv gedruckten Parameter sind:  
  
 `id`  
 Bezeichner des Steuerelements, das die Benachrichtigung gesendet.  Nicht verwendet.  Die Steuerelement\-ID wird von der **NMHDR**\-Struktur ausgeführt.  
  
 `pNMHDR`  
 Ein Zeiger auf [NMTTDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760258)\-Struktur.  Diese Struktur wird auch in [Die TOOLTIPTEXT\-Struktur](../mfc/tooltiptext-structure.md) weiter erläutert.  
  
 `pResult`  
 Ein Zeiger, an führen Code, den Sie festlegen können, bevor Sie zurückkehren.  **TTN\_NEEDTEXT** Sie können den Parameter `pResult` ignorieren.  
  
 Als Beispiel für einen Formularansichtsbenachrichtigungshandler:  
  
 [!CODE [NVC_MFCControlLadenDialog#54](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#54)]  
  
 Aufruf `EnableToolTips` \(dieses Fragment die der `OnInitDialog`\):  
  
 [!CODE [NVC_MFCControlLadenDialog#55](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#55)]  
  
## Siehe auch  
 [QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)