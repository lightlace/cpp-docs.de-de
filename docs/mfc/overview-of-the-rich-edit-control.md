---
title: Übersicht über das RichEdit-Steuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rich edit controls [MFC]
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7598449539fffdc2a8a4248fe02b29c83a2d2dfe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387095"
---
# <a name="overview-of-the-rich-edit-control"></a>Übersicht über das RichEdit-Steuerelement

> [!IMPORTANT]
>  Wenn Sie ein rich-Edit-Steuerelement in einem Dialogfeld verwenden (unabhängig davon, ob Ihre Anwendung SDI, MDI oder Dialogfeldern basierende), rufen Sie [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) nach bevor das Dialogfeld im Feld angezeigt wird. Ein typische Ort zum Aufrufen dieser Funktion ist in Ihres Programms `InitInstance` Member-Funktion. Sie müssen nicht jedes Mal nenne Sie das Dialogfeld nur beim ersten anzeigen. Sie müssen keine Aufrufen `AfxInitRichEdit` bei Verwendung mit `CRichEditView`.

Rich-edit-Steuerelemente ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) bieten eine Programmierschnittstelle für die textformatierung. Allerdings muss eine Anwendung Komponenten der Benutzeroberfläche erforderlich, um Formatierungsvorgängen für den Benutzer verfügbar zu machen implementieren. D. h. das Rich-edit Steuerelement unterstützt das Ändern der Zeichen- oder Absatz Attribute des ausgewählten Texts. Einige Beispiele für Zeichen, die Attribute sind fett, kursiv, Schriftfamilie und Schriftgrad. Beispiele für Absatzattribute enthalten Alignment, Margin und Tabstopps. Es ist jedoch entscheiden, ob Sie die Benutzeroberfläche bereitstellen, ob das Symbolleisten-Schaltflächen, Menüelemente oder ein Dialogfeld Format Zeichen ist. Es gibt auch Funktionen zum Abfragen der rich-Edit-Steuerelement für die Attribute der aktuellen Auswahl. Verwenden Sie diese Funktionen zum Anzeigen der aktuellen Einstellungen für die Attribute, z. B. ein Häkchen auf dem UI-Befehl festlegen, wenn die Auswahl die fett formatierten zeichenformatierung-Attribut aufweist.

Weitere Informationen zu Zeichen- und absatzformatierung, finden Sie unter [Zeichenformatierung](../mfc/character-formatting-in-rich-edit-controls.md) und [Absatzformatierung](../mfc/paragraph-formatting-in-rich-edit-controls.md) weiter unten in diesem Thema.

Rich-edit-Steuerelemente unterstützt fast alle Vorgänge und Nachrichten mit mehrzeilige Bearbeitungssteuerelemente verwendet. Daher edit Anwendungen, die bereits Bearbeitungssteuerelemente verwenden einfach geändert werden können zur Verwendung von Rich-Steuerelemente. Zusätzliche Meldungen und Benachrichtigungen ermöglichen den Zugriff auf die die Funktionalität nur für rich-Edit-Steuerelemente. Weitere Informationen zu Bearbeitungssteuerelementen, finden Sie unter [CEdit](../mfc/reference/cedit-class.md).

Weitere Informationen zu den Benachrichtigungen, finden Sie unter [Benachrichtigungen von einem RichEdit-Steuerelement](../mfc/notifications-from-a-rich-edit-control.md) weiter unten in diesem Thema.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

