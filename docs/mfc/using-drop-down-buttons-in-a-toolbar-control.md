---
title: "Verwenden von DropDown-Schaltfl&#228;chen in einem Symbolleisten-Steuerelement"
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
  - "TBN_DROPDOWN"
  - "TBSTYLE_EX_DRAWDDARROWS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl-Klasse, Dropdown-Schaltflächen"
  - "Dropdown-Schaltflächen in Symbolleisten"
  - "TBN_DROPDOWN-Benachrichtigung"
  - "TBSTYLE_EX_DRAWDDARROWS"
  - "Symbolleisten [C++], Dropdown-Schaltflächen"
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von DropDown-Schaltfl&#228;chen in einem Symbolleisten-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Neben den Standardschaltflächen kann eine Symbolleiste Dropdownschaltflächen verfügen.  Eine Dropdown\-Schaltfläche wird normalerweise durch das Vorhandensein eines angefügten Pfeils nach unten angegeben.  
  
> [!NOTE]
>  Der angefügte Pfeil nach unten angezeigt, wenn das `TBSTYLE_EX_DRAWDDARROWS` erweiterte Format festgelegt wurde.  
  
 Wenn der Benutzer auf diesen Pfeil klicken \(oder die Schaltfläche selbst, wenn kein Pfeil vorhanden ist\), wird `TBN_DROPDOWN` eine Benachrichtigung übergeordnete Element des Symbolleisten\-Steuerelements gesendet.  Sie können diese Benachrichtigung dann bearbeiten und ein Popupmenü anzeigen; ähnlich dem Verhalten von Internet Explorer.  
  
 Das folgende Verfahren veranschaulicht, wie eine mit Dropdown\-Symbolleistenschaltfläche Popupmenü implementiert:  
  
### So eine Dropdownschaltfläche implementieren  
  
1.  Nachdem `CToolBarCtrl`\-Objekt erstellt wurde, legen Sie das `TBSTYLE_EX_DRAWDDARROWS` \- Format, mit dem folgenden Code fest:  
  
     [!CODE [NVC_MFCControlLadenDialog#36](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#36)]  
  
2.  Legen Sie das `TBSTYLE_DROPDOWN` \- Format für alle neuen \([InsertButton](../Topic/CToolBarCtrl::InsertButton.md) oder [AddButtons](../Topic/CToolBarCtrl::AddButtons.md)\) oder vorhandenen \([SetButtonInfo](../Topic/CToolBarCtrl::SetButtonInfo.md)\) Schaltflächen fest, die Dropdownschaltflächen sind.  Im folgenden Beispiel wird das Ändern einer vorhandenen Schaltfläche in einem `CToolBarCtrl`\-Objekt:  
  
     [!CODE [NVC_MFCControlLadenDialog#37](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#37)]  
  
3.  Fügen Sie einen Handler `TBN_DROPDOWN` der übergeordneten Klasse des Symbolleistenobjekts hinzu.  
  
     [!CODE [NVC_MFCControlLadenDialog#38](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#38)]  
  
4.  Im neuen Handler zeigen Sie das entsprechende Popupmenü an.  Im folgenden Code wird eine Methode:  
  
     [!CODE [NVC_MFCControlLadenDialog#39](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#39)]  
  
## Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)