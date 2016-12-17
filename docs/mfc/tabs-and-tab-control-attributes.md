---
title: "Registerkarten und Attribute von Registerkarten-Steuerelementen"
ms.custom: na
ms.date: "12/14/2016"
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
  - "Attribute [C++], Referenzthemen"
  - "CTabCtrl-Klasse, Registerkarte-Steuerelementattribut"
  - "Registerkarten-Steuerelemente, Attribute"
  - "Registerkarten"
  - "Registerkarten, Attribute"
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Registerkarten und Attribute von Registerkarten-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie haben beträchtliches Kontrolle über das Aussehen und Verhalten der Registerkarten, die ein Tab\-Steuerelement \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\) besteht.  Jede Registerkarte kann eine Bezeichnung, ein Symbol, einen Elementzustand und anwendungsdefinierten einen 32\-Bit\-Wert haben, der ihr zugeordnet wird.  Für jede Registerkarte können Sie das Symbol, die Bezeichnung oder beides anzeigen.  
  
 Darüber hinaus kann jedes Registerelement drei mögliche Status haben: gedrückt, nicht aktiviert oder hervorgehoben.  Dieser Zustand kann nur festgelegt werden, indem ein vorhandenes Registerkartenelement ändert.  Um ein vorhandenes Registerkartenelement zu ändern, rufen Sie es mit einem Aufruf von [GetItem](../Topic/CTabCtrl::GetItem.md) ab, ändern Sie die `TCITEM`\-Struktur \(insbesondere der Datenmember **dwState** und **dwStateMask** \), und geben Sie dann die geänderten `TCITEM`\-Struktur mit einem Aufruf der [SetItem](../Topic/CTabCtrl::SetItem.md) zurück.  Wenn Sie die den Elementzustand aller Aufgaben müssen, wenden die in `CTabCtrl` enthaltenen Registerkartenelemente ein [DeselectAll](../Topic/CTabCtrl::DeselectAll.md), machen einen Aufruf.  Diese Funktion setzt den Zustand aller Registerkartenelemente oder aller Elemente außer derzeit ausgewählte das zurück.  
  
 Der folgende Code stellt den Zustand aller Registerkartenelementen frei und ändert den Zustand des dritten Elements:  
  
 [!CODE [NVC_MFCControlLadenDialog#32](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#32)]  
  
 Weitere Informationen über Registerkartenattribute, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Registerkarten und Registerkarten\-Attribute](http://msdn.microsoft.com/library/windows/desktop/bb760550).  Weitere Informationen über das Hinzufügen von Tabstopps in einem Registersteuerelement, finden Sie unter [Hinzufügen von Tabstopps in einem Registersteuerelement](../mfc/adding-tabs-to-a-tab-control.md) weiter unten in diesem Thema.  
  
## Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)