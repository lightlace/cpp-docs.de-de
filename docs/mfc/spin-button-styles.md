---
title: Drehfeld-Schaltflächenstile
ms.date: 09/09/2019
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
ms.openlocfilehash: 1aae4b7e4c63929ebe03c97d50f05754bc13ec26
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907858"
---
# <a name="spin-button-styles"></a>Drehfeld-Schaltflächenstile

Viele der Einstellungen für eine Dreh Schaltfläche ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) werden durch Stile gesteuert. Sie können die folgenden Stile mithilfe des [Klassen-Assistenten](reference/mfc-class-wizard.md)festlegen.

- **Ausrichtung** Entweder vertikal oder horizontal. Steuert die Ausrichtung der Pfeil Schaltflächen. Wird dem UDS_HORZ-Stil zugeordnet.

- **Ausrichtung** Eins von nicht angefügt, Links oder rechts. Steuert die Position der Drehfeld Schaltfläche. Links und rechts die Dreh Schaltfläche neben dem Buddy-Fenster. Die Breite des Buddy-Fensters wird verringert, um die Dreh Schaltfläche zu erfüllen. Die den Formaten UDS_ALIGNLEFT und UDS_ALIGNRIGHT zugeordnet sind.

- **Autobuddy** Wählt automatisch das vorherige Fenster in Z-Order als Buddy-Fenster auf die Drehfeld Schaltfläche aus. In einer Dialogfeld Vorlage ist dies das Steuerelement, das der Dreh Schaltfläche in der Aktivier Reihenfolge vorausgeht. Wird dem UDS_AUTOBUDDY-Stil zugeordnet.

- **Festlegen von Buddy Integer** Bewirkt, dass das Drehfeld-Steuerelement die Beschriftung des Buddy-Fensters erhöht und Dekrement, wenn sich die aktuelle Position ändert. Wird dem UDS_SETBUDDYINT-Stil zugeordnet.

- **Keine tausend** Fügt das Tausender Trennzeichen nicht in den Wert der Beschriftung des Buddy-Fensters ein. Wird dem UDS_NOTHOUSANDS-Stil zugeordnet.

    > [!NOTE]
    >  Legen Sie diesen Stil fest, wenn Sie den ganzzahligen Wert aus dem Buddy-Steuerelement mit dem Dialog Datenaustausch (DDX) erhalten möchten. `DDX_Text`akzeptiert keine eingebetteten Tausender Trennzeichen.

- Umbruch Bewirkt, dass die Position "Wrap" ist, wenn der Wert über den Bereich des Steuer Elements hinaus erhöht oder dekrementiert wird. Wird dem UDS_WRAP-Stil zugeordnet.

- **Pfeiltasten** Bewirkt, dass die Drehungs Schaltfläche die Position erhöht oder dekretert, wenn die nach-oben-und nach-unten-Taste gedrückt wird. Wird dem UDS_ARROWKEYS-Stil zugeordnet.

## <a name="see-also"></a>Siehe auch

[Verwenden von CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
