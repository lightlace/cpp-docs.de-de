---
title: "Memberfunktionen f&#252;r das Drehfeldsteuerelement | Microsoft Docs"
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
  - "CSpinButtonCtrl-Klasse, Methoden"
  - "Drehfeld-Steuerelement, Methoden"
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Memberfunktionen f&#252;r das Drehfeldsteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt mehrere Memberfunktionen, die für das Drehfeld\-Steuerelement \([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)\) verfügbar sind.  Verwenden Sie diese Funktionen, um die folgenden Attribute des Drehfelds zu ändern.  
  
-   **Beschleunigung** können Sie die Rate anpassen, an der die Position ändert, wenn der Benutzer die Pfeilschaltfläche gedrückt hält.  Um mit Beschleunigung zu umgehen, verwenden Sie die [SetAccel](../Topic/CSpinButtonCtrl::SetAccel.md) und [GetAccel](../Topic/CSpinButtonCtrl::GetAccel.md)\-Memberfunktionen.  
  
-   **Basis** Sie können ändern die Basis \(entweder 10 oder 16\) verwendet, um Position in der Beschriftung des Buddyfensters anzuzeigen.  Um mit der Basis zu umgehen, verwenden Sie die [GetBase](../Topic/CSpinButtonCtrl::GetBase.md) und [SetBase](../Topic/CSpinButtonCtrl::SetBase.md)\-Memberfunktionen.  
  
-   **Buddyfenster** Sie können das Buddyfenster dynamisch festlegen.  Um Abfragen und Ändern die das Steuerelement Buddyfenster ist, verwenden Sie die [GetBuddy](../Topic/CSpinButtonCtrl::GetBuddy.md) und [SetBuddy](../Topic/CSpinButtonCtrl::SetBuddy.md)\-Memberfunktionen.  
  
-   **Position** Sie können die Position abfragen und ändern.  Um direkt mit Position zu umgehen, verwenden Sie die [GetPos](../Topic/CSpinButtonCtrl::GetPos.md) und [SetPos](../Topic/CSpinButtonCtrl::SetPos.md)\-Memberfunktionen.  Wenn die Beschriftung des Buddysteuerelements möglicherweise geändert \(beispielsweise, im Fall, dass der Buddy ein Bearbeitungssteuerelement ist\), erhält `GetPos` die aktuelle Beschriftung und passt die Position entsprechend.  
  
-   **Bereich** Sie können den Maximal\- und Minimalwert Position für das Drehfeld ändern.  Standardmäßig wird das Maximum auf 0 festgelegt, und das minimale wird 100 festgelegt.  Da das Standardmaximum kleiner als das Standardminimum ist, ist die Aktionen der Pfeilschaltflächen kontraintuitiv.  In der Regel legen Sie den Bereich mit der Memberfunktion [SetRange](../Topic/CSpinButtonCtrl::SetRange.md) fest.  Um die [GetRange](../Topic/CSpinButtonCtrl::GetRange.md) Bereichsverwendung abfragen.  
  
## Siehe auch  
 [Verwenden von CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)