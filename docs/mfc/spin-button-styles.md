---
title: "Drehfeld-Schaltflächenstile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa4b2ae42175e2d4fc2ddb3317ef76b6b4dec8d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="spin-button-styles"></a>Drehfeld-Schaltflächenstile
Viele der Einstellungen für ein Drehfeld ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) von Stilen gesteuert werden. Sie können festlegen, dass die folgenden Formate, die mit der **Eigenschaften** Fenster in den Dialog-Editor.  
  
-   **Ausrichtung** entweder vertikal oder Horizontal. Steuert die Ausrichtung der Pfeiltasten an. Zugeordnete der `UDS_HORZ` Stil.  
  
-   **Ausrichtung** getrennt, links oder rechts. Steuert den Speicherort für das Drehfeld. Positionieren das Drehfeld neben dem Buddyfenster, links und rechts. Die Breite des Fensters Buddy wird verringert, um das Drehfeld aufzunehmen. Zugeordnete der `UDS_ALIGNLEFT` und `UDS_ALIGNRIGHT` Stile.  
  
-   **Auto-Buddy** wählt automatisch den vorherige Fenster in Z-Reihenfolge als Buddyfenster, um das Drehfeld. In einer Dialogfeldvorlage ist dies die steuern, die welche das Drehfeld in der Aktivierreihenfolge vorangestellt. Zugeordnete der `UDS_AUTOBUDDY` Stil.  
  
-   **Legen Sie Buddy-Integer** bewirkt, dass das Drehfeld-Steuerelement zum Inkrementieren und Dekrementieren die Beschriftung des Fensters Buddy als die aktuelle Position ändert sich. Zugeordnete der `UDS_SETBUDDYINT` Stil.  
  
-   **Keine Tausende** werden keine Tausendertrennzeichen eingefügt Trennzeichen in der die Beschriftung des Fensters Buddy-Werten. Zugeordnete der `UDS_NOTHOUSANDS` Stil.  
  
    > [!NOTE]
    >  Legen Sie dieses Format, wenn Dialogdatenaustausch (DDX) zu verwenden, um den ganzzahligen Wert aus dem Buddysteuerelement abgerufen werden sollen. `DDX_Text`nimmt keine eingebettete Tausendertrennzeichen an.  
  
-   **Umschließen** bewirkt, dass die Position, um "binden", wie der Wert inkrementiert oder dekrementiert außerhalb des gültigen Bereichs des Steuerelements ist. Zugeordnete der `UDS_WRAP` Stil.  
  
-   **Pfeiltasten** bewirkt, dass das Drehfeld, um inkrementiert oder dekrementiert die Position, wenn die nach-oben und nach-unten-Taste gedrückt wird. Zugeordnete der `UDS_ARROWKEYS` Stil.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

