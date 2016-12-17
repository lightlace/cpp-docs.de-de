---
title: "Verwenden von QuickInfos in einem CStatusBarCtrl-Objekt"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl-Klasse, QuickInfos"
  - "Statusleisten, QuickInfos"
  - "QuickInfos [C++], Verwenden in Statusleiste"
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von QuickInfos in einem CStatusBarCtrl-Objekt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um QuickInfo für ein StatusBar\-Steuerelement zu aktivieren, erstellen Sie das `CStatusBarCtrl`\-Objekt mit dem **SBT\_TOOLTIPS** Format.  
  
> [!NOTE]
>  Wenn Sie ein `CStatusBar`\-Objekt verwenden, um die Statusleiste zu implementieren, verwenden Sie die `CStatusBar::CreateEx`\-Funktion.  Sie ermöglicht es Ihnen, zusätzliche Formaten für das eingebettete Objekt **CStatusBarCtrl**  angeben.  
  
 Sobald das `CStatusBarCtrl`\-Objekt erfolgreich erstellt wurde, dem [CStatusBarCtrl::SetTipText](../Topic/CStatusBarCtrl::SetTipText.md) und [CStatusBarCtrl::GetTipText](../Topic/CStatusBarCtrl::GetTipText.md), den QuickInfo\-Text für einen bestimmten Gültigkeitsbereich festzulegen und abzurufen.  
  
 Sobald die QuickInfo festgelegt wurde, ist sie nur angezeigt, wenn ein Teil ein Symbol und keinen Text oder wenn Text aller nicht innerhalb des Teils angezeigt werden kann.  QuickInfos werden nicht in einfachen Modus unterstützt.  
  
## Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)