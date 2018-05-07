---
title: Verwenden von Standardsteuerelementen in einem Dialogfeld | Microsoft Docs
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
ms.openlocfilehash: c848cfa74363d871720f9ca269b114687aad9ecf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-common-controls-in-a-dialog-box"></a>Verwenden von Standardsteuerelementen in einem Dialogfeld
Die allgemeine Windows-Steuerelemente können verwendet werden, [Dialogfelder](../mfc/dialog-boxes.md), Ansichten, Datensatzansichten und ein anderes Fenster, die basierend auf einer Dialogfeldvorlage bilden. Die folgende Prozedur, mit nur geringfügigen Änderungen funktioniert für Formulare ebenfalls.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-use-a-common-control-in-a-dialog-box"></a>Verwenden ein allgemeinen Steuerelements in einem Dialogfeld  
  
1.  Platzieren Sie das Steuerelement auf der Dialogfeldvorlage [mit dem Dialog-Editor](../mfc/using-the-dialog-editor-to-add-controls.md).  
  
2.  Hinzufügen der Dialogfeldklasse eine Membervariable, die das Steuerelement darstellt. In der **Hinzufügen von Membervariablen** überprüfen Sie im Dialogfeld **Steuerelementvariable** und sicherstellen, dass **Steuerelement** ausgewählt ist, für die **Kategorie**.  
  
3.  Wenn diese Standardsteuerelements Eingabe für die Anwendung bereitstellt, deklarieren Sie zusätzliche Member Variable(s) in Dialogklasse, behandeln die Eingabewerte.  
  
    > [!NOTE]
    >  Sie können diese über das Kontextmenü in der Klassenansicht Membervariablen hinzufügen (siehe [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)).  
  
4.  In [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) für Ihre Dialogfeldklasse, die anfängliche Bedingungen für das allgemeine Steuerelement festlegen. Verwenden die Membervariable, die im vorherigen Schritt erstellt haben, verwenden Sie die Memberfunktionen Anfangswert und andere Einstellungen festlegen. Finden Sie unter den folgenden Beschreibungen der Steuerelemente für Details zu den Einstellungen ein.  
  
     Sie können auch [Dialogdatenaustausch](../mfc/dialog-data-exchange-and-validation.md) (DDX), um Steuerelemente in einem Dialogfeld zu initialisieren.  
  
5.  Verwenden Sie im Handler für Steuerelemente im Dialogfeld die Membervariable auf um das Steuerelement zu bearbeiten. Finden Sie zu Methoden in der folgenden Beschreibungen der Steuerelemente für Details.  
  
    > [!NOTE]
    >  Die Membervariable ist vorhanden, nur so lange im Dialogfeld selbst vorhanden ist. Sie werden nicht des Steuerelements für die Eingabewerte Abfragen, nachdem Sie das Dialogfeld geschlossen wurde. Zum Arbeiten mit Eingabewerten aus eines allgemeinen Steuerelements überschreiben `OnOK` in der Dialogfeldklasse. Klicken Sie in der Außerkraftsetzung Fragen Sie des Steuerelements für die Eingabewerte ab, und speichern Sie diese Werte in Membervariablen der Dialogfeldklasse.  
  
    > [!NOTE]
    >  Sie können auch Dialogdatenaustausch festlegen oder Abrufen von Werten aus den Steuerelementen in einem Dialogfeld.  
  
## <a name="remarks"></a>Hinweise  
 Das Hinzufügen von einigen allgemeinen Steuerelementen in einem Dialogfeld führt dazu, dass das Dialogfeld nicht mehr funktioniert. Verweisen auf [Hinzufügen von Steuerelementen zu einem Dialogfeld bewirkt, dass das Dialogfeld nicht mehr Funktion](../windows/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md) für Weitere Informationen zur Behandlung dieser Situation.  
  
## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun  
  
-   [Hinzufügen von Steuerelementen zu einem Dialogfeld manuell statt mit dem Dialog-editor](../mfc/adding-controls-by-hand.md)  
  
-   [Eines der allgemeinen Windows-Standardsteuerelemente Meine Steuerelements abgeleitet](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [Verwenden eines Standardsteuerelements als untergeordnetes Fenster](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [Empfangen von benachrichtigungsmeldungen aus einem Steuerelement](../mfc/receiving-notification-from-common-controls.md)  
  
-   [Dialogdatenaustausch (DDX) verwenden](../mfc/dialog-data-exchange-and-validation.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

