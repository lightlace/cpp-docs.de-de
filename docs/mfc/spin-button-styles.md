---
title: Drehfeld-Schaltflächenstile | Microsoft-Dokumentation
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
ms.openlocfilehash: 71da44858ea018d0393af6267e4bb522a2c57391
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393593"
---
# <a name="spin-button-styles"></a>Drehfeld-Schaltflächenstile

Viele der Einstellungen für ein Drehfeld ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) von Stilen gesteuert werden. Sie können festlegen, dass die folgenden Formate, die mit der **Eigenschaften** -Fensters im Dialog-Editor.

- **Ausrichtung** entweder vertikal oder Horizontal. Steuert die Ausrichtung der Pfeiltasten an. Styl UDS_HORZ zugeordnet ist.

- **Ausrichtung** eines getrennt, links oder rechts. Steuert den Speicherort der die Schaltfläche "starten". Links und rechts positionieren das Drehfeld neben dem Buddyfenster. Die Breite des Buddy-Fensters wird verringert, um die Schaltfläche "starten" zu ermöglichen. Die Stile UDS_ALIGNLEFT und UDS_ALIGNRIGHT zugeordnet ist.

- **Auto Buddy** wählt automatisch die vorherige Fenster, in der Z-Reihenfolge, als Buddy-Fenster auf die Schaltfläche "starten". In einer Dialogfeldvorlage ist dies das Steuerelement mit dem die Schaltfläche "starten" in der Reihenfolge vor. Styl UDS_AUTOBUDDY zugeordnet ist.

- **Legen Sie Buddy Integer** bewirkt, dass das Drehfeld-Steuerelement zum Inkrementieren und Dekrementieren die Beschriftung des Buddy-Fensters, wenn sich die aktuelle Position ändert. Styl UDS_SETBUDDYINT zugeordnet ist.

- **Keine Tausende** werden keine Tausendertrennzeichen eingefügt Trennzeichen in den Wert in der Beschriftung des Buddy-Fensters. Styl UDS_NOTHOUSANDS zugeordnet ist.

    > [!NOTE]
    >  Festlegen Sie dieser Stil, sollten Sie Dialogdatenaustausch (DDX) verwenden, um den ganzzahligen Wert aus dem Buddysteuerelement zu erhalten. `DDX_Text` nimmt keine eingebettete Tausendertrennzeichen an.

- **Umschließen** bewirkt, dass die Position, die "wrap", wie der Wert inkrementiert oder dekrementiert außerhalb des Gültigkeitsbereichs für das Steuerelement ist. Styl UDS_WRAP zugeordnet ist.

- **Pfeiltasten** bewirkt, dass die Drehfeld-Schaltfläche, um inkrementiert oder dekrementiert die Position, wenn die nach-oben und nach-unten-Tasten gedrückt werden. Styl UDS_ARROWKEYS zugeordnet ist.

## <a name="see-also"></a>Siehe auch

[Verwenden von CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

