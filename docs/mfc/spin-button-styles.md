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
ms.openlocfilehash: 223b7e0875a5382edf5f4d350c9343d117768c41
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953777"
---
# <a name="spin-button-styles"></a>Drehfeld-Schaltflächenstile
Viele der Einstellungen für ein Drehfeld ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) von Stilen gesteuert werden. Sie können festlegen, dass die folgenden Formate, die mit der **Eigenschaften** Fenster in den Dialog-Editor.  
  
-   **Ausrichtung** entweder vertikal oder Horizontal. Steuert die Ausrichtung der Pfeiltasten an. Das Format UDS_HORZ zugeordnet ist.  
  
-   **Ausrichtung** getrennt, links oder rechts. Steuert den Speicherort für das Drehfeld. Positionieren das Drehfeld neben dem Buddyfenster, links und rechts. Die Breite des Fensters Buddy wird verringert, um das Drehfeld aufzunehmen. Die Stile UDS_ALIGNLEFT und UDS_ALIGNRIGHT zugeordnet ist.  
  
-   **Auto-Buddy** wählt automatisch den vorherige Fenster in Z-Reihenfolge als Buddyfenster, um das Drehfeld. In einer Dialogfeldvorlage ist dies die steuern, die welche das Drehfeld in der Aktivierreihenfolge vorangestellt. Das Format UDS_AUTOBUDDY zugeordnet ist.  
  
-   **Legen Sie Buddy-Integer** bewirkt, dass das Drehfeld-Steuerelement zum Inkrementieren und Dekrementieren die Beschriftung des Fensters Buddy als die aktuelle Position ändert sich. Das Format UDS_SETBUDDYINT zugeordnet ist.  
  
-   **Keine Tausende** werden keine Tausendertrennzeichen eingefügt Trennzeichen in der die Beschriftung des Fensters Buddy-Werten. Das Format UDS_NOTHOUSANDS zugeordnet ist.  
  
    > [!NOTE]
    >  Legen Sie dieses Format, wenn Dialogdatenaustausch (DDX) zu verwenden, um den ganzzahligen Wert aus dem Buddysteuerelement abgerufen werden sollen. `DDX_Text` nimmt keine eingebettete Tausendertrennzeichen an.  
  
-   **Umschließen** bewirkt, dass die Position, um "binden", wie der Wert inkrementiert oder dekrementiert außerhalb des gültigen Bereichs des Steuerelements ist. Das Format UDS_WRAP zugeordnet ist.  
  
-   **Pfeiltasten** bewirkt, dass das Drehfeld, um inkrementiert oder dekrementiert die Position, wenn die nach-oben und nach-unten-Taste gedrückt wird. Das Format UDS_ARROWKEYS zugeordnet ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

