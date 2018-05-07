---
title: Drehfeld-Schaltflächenstile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 96b559fcda4825aec71ba4b5c1dd8c3cd319b83d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="spin-button-styles"></a>Drehfeld-Schaltflächenstile
Viele der Einstellungen für ein Drehfeld ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) von Stilen gesteuert werden. Sie können festlegen, dass die folgenden Formate, die mit der **Eigenschaften** Fenster in den Dialog-Editor.  
  
-   **Ausrichtung** entweder vertikal oder Horizontal. Steuert die Ausrichtung der Pfeiltasten an. Zugeordnete der `UDS_HORZ` Stil.  
  
-   **Ausrichtung** getrennt, links oder rechts. Steuert den Speicherort für das Drehfeld. Positionieren das Drehfeld neben dem Buddyfenster, links und rechts. Die Breite des Fensters Buddy wird verringert, um das Drehfeld aufzunehmen. Zugeordnete der `UDS_ALIGNLEFT` und `UDS_ALIGNRIGHT` Stile.  
  
-   **Auto-Buddy** wählt automatisch den vorherige Fenster in Z-Reihenfolge als Buddyfenster, um das Drehfeld. In einer Dialogfeldvorlage ist dies die steuern, die welche das Drehfeld in der Aktivierreihenfolge vorangestellt. Zugeordnete der `UDS_AUTOBUDDY` Stil.  
  
-   **Legen Sie Buddy-Integer** bewirkt, dass das Drehfeld-Steuerelement zum Inkrementieren und Dekrementieren die Beschriftung des Fensters Buddy als die aktuelle Position ändert sich. Zugeordnete der `UDS_SETBUDDYINT` Stil.  
  
-   **Keine Tausende** werden keine Tausendertrennzeichen eingefügt Trennzeichen in der die Beschriftung des Fensters Buddy-Werten. Zugeordnete der `UDS_NOTHOUSANDS` Stil.  
  
    > [!NOTE]
    >  Legen Sie dieses Format, wenn Dialogdatenaustausch (DDX) zu verwenden, um den ganzzahligen Wert aus dem Buddysteuerelement abgerufen werden sollen. `DDX_Text` nimmt keine eingebettete Tausendertrennzeichen an.  
  
-   **Umschließen** bewirkt, dass die Position, um "binden", wie der Wert inkrementiert oder dekrementiert außerhalb des gültigen Bereichs des Steuerelements ist. Zugeordnete der `UDS_WRAP` Stil.  
  
-   **Pfeiltasten** bewirkt, dass das Drehfeld, um inkrementiert oder dekrementiert die Position, wenn die nach-oben und nach-unten-Taste gedrückt wird. Zugeordnete der `UDS_ARROWKEYS` Stil.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

