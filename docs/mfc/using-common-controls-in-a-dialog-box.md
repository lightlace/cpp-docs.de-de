---
title: Verwenden von Standardsteuerelementen in einem Dialogfeld | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- dialog box controls [MFC], common controls
- Windows common controls [MFC], in dialog boxes
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8d3db1d8c19b68adb8cec53984e0dfe5a189651
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389864"
---
# <a name="using-common-controls-in-a-dialog-box"></a>Verwenden von Standardsteuerelementen in einem Dialogfeld

Die Windows-Standardsteuerelemente in verwendet werden können [Dialogfelder](../mfc/dialog-boxes.md), Ansichten, Datensatzansichten und einem anderen Fenster, die basierend auf einer Dialogfeldvorlage zu bilden. Die folgenden Verfahren mit kleinen Änderungen funktionieren für Formulare sowie.

## <a name="procedures"></a>Verfahren

#### <a name="to-use-a-common-control-in-a-dialog-box"></a>Verwenden ein Standardsteuerelements in einem Dialogfeld

1. Platzieren Sie das Steuerelement auf der Dialogfeldvorlage [mithilfe des Dialog-Editors](../mfc/using-the-dialog-editor-to-add-controls.md).

1. Fügen Sie eine Membervariable, die das Steuerelement darstellt, auf die Dialogfeldklasse. In der **Hinzufügen von Membervariablen** Kontrollkästchen **Steuerungsvariable** und sicherstellen, dass **Steuerelement** ausgewählt ist, für die **Kategorie**.

1. Wenn diese Standardsteuerelements Eingabe für die Anwendung bereitstellt, deklarieren Sie zusätzliche Member Variable(s) in die Dialogfeldklasse, behandeln die Eingabewerte.

    > [!NOTE]
    >  Sie können diese Membervariablen, die über das Kontextmenü in der Klassenansicht hinzufügen (siehe [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)).

1. In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) legen Sie die anfänglichen Bedingung für das allgemeine Steuerelement für die Dialogfeldklasse. Verwenden Sie die Membervariable, die im vorherigen Schritt erstellt haben, die Memberfunktionen Anfangswert und andere Einstellungen festlegen. Finden Sie unter den folgenden Beschreibungen der Steuerelemente für Details zu den Einstellungen ein.

     Sie können auch [Dialogdatenaustausch](../mfc/dialog-data-exchange-and-validation.md) (DDX), um Steuerelemente in einem Dialogfeld zu initialisieren.

1. Können Sie die Membervariable im Handler für Steuerelemente im Dialogfeld um das Steuerelement zu bearbeiten. Die folgenden Beschreibungen der Steuerelemente für Details auf Methoden angezeigt.

    > [!NOTE]
    >  Die Membervariable ist vorhanden, nur so lange vorhanden, das Dialogfeld ist. Es werden nicht möglich, das Steuerelement für die Eingabewerte abzufragen, nachdem Sie das Dialogfeld geschlossen wurde. Zum Arbeiten mit der Eingabewerten aus einem allgemeinen Steuerelement außer Kraft setzen `OnOK` in der Dialogfeldklasse. Fragen Sie in der Außerkraftsetzung des Steuerelements für die Eingabewerte ab aus, und speichern Sie diese Werte in Membervariablen der Dialogfeldklasse.

    > [!NOTE]
    >  Sie können auch die Dialogfeld-Datenaustausch verwenden, festlegen oder Abrufen von Werten aus den Steuerelementen in einem Dialogfeld.

## <a name="remarks"></a>Hinweise

Das Hinzufügen von einigen allgemeinen Steuerelementen auf ein Dialogfeld, das bewirkt, dass das Dialogfeld nicht mehr funktioniert. Finden Sie unter [Hinzufügen von Steuerelementen zu einem Dialogfeld bewirkt, dass das Dialogfeld nicht mehr Funktion](../windows/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md) für Weitere Informationen zur Behandlung dieser Situation.

## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun

- [Hinzufügen von Steuerelementen zu einem Dialogfeld manuell statt mit dem Dialog-editor](../mfc/adding-controls-by-hand.md)

- [Eines der allgemeinen Windows-Standardsteuerelemente mein Steuerelement abgeleitet](../mfc/deriving-controls-from-a-standard-control.md)

- [Verwenden eines Standardsteuerelements als untergeordnetes Fenster](../mfc/using-a-common-control-as-a-child-window.md)

- [Empfangen von benachrichtigungsmeldungen aus einem Steuerelement](../mfc/receiving-notification-from-common-controls.md)

- [Dialogdatenaustausch (DDX) verwenden](../mfc/dialog-data-exchange-and-validation.md)

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

