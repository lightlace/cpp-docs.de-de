---
title: Stile für das Statussteuerelement
ms.date: 11/19/2018
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
ms.openlocfilehash: 3adbd32456b1375bd2dc8574220e083ca3d83ee9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306813"
---
# <a name="styles-for-the-progress-control"></a>Stile für das Statussteuerelement

Beim anfänglichen Erstellen des Statussteuerelements ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md#create)), verwenden Sie die *DwStyle* Parameter an die gewünschte Window-Stile für das Steuerelement ausgeführt. Die folgende Liste enthält die entsprechenden Window-Stile. Das Steuerelement ignoriert den Stil für alle Fenster nur die hier aufgeführten. Sie sollten immer als untergeordnetes Fenster, in der Regel von einem Dialogfeld übergeordnetes Element des Steuerelements erstellen.

|Fensterstil|Effekt|
|------------------|------------|
|WS_BORDER|Erstellt einen Rahmen um das Fenster.|
|WS_CHILD|Erstellt ein untergeordnetes Fenster (sollte stets verwendet werden, für die `CProgressCtrl`).|
|WS_CLIPCHILDREN|Schließt den Bereich, die durch untergeordnete Fenster belegt wird, wenn Sie innerhalb des übergeordneten Fensters zeichnen. Wird verwendet, wenn Sie das übergeordnete Fenster erstellen.|
|WS_CLIPSIBLINGS|Untergeordnete Fenster relativ zueinander.|
|WS_DISABLED|Erstellt ein Fenster, das anfänglich deaktiviert ist.|
|WS_VISIBLE|Erstellt ein Fenster, das anfänglich sichtbar ist.|
|WS_TABSTOP|Gibt an, dass das Steuerelement den Fokus erhalten kann, wenn der Benutzer verschieben, die TAB-Taste drückt.|

Darüber hinaus können Sie zwei Formate, die nur für das Statussteuerelement gelten PBS_VERTICAL und PBS_SMOOTH angeben.

Verwenden Sie PBS_VERTICAL, um das Steuerelement vertikal statt horizontal zu orientieren. Verwenden Sie PBS_SMOOTH, um das Steuerelement vollständig zu füllen, anstatt kleine getrennte Quadrate, die inkrementell des Steuerelements ausfüllen anzuzeigen.

Ohne PBS_SMOOTH-Format:

![Standardstil der Statusleiste](../mfc/media/vc4ruw1.gif "Standardstil der Statusleiste")

Mit PBS_SMOOTH und PBS_VERTICAL-Formate:

![Format, glatt und vertikal-Statusleiste](../mfc/media/vc4ruw2.gif "Format, glatt und vertikal-Statusleiste")

Weitere Informationen finden Sie unter [Window-Stile](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) in die *MFC-Referenz*.

## <a name="see-also"></a>Siehe auch

[Verwenden von CProgressCtrl](../mfc/using-cprogressctrl.md)
