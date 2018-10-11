---
title: Hinzufügen eines Ereignishandlers (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd16628c48c30f6f554a842b70c5217753e305f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430305"
---
# <a name="adding-an-event-handler-visual-c"></a>Hinzufügen eines Ereignishandlers (Visual C++)

Sie können einen neuen Ereignishandler über den Ressourcen-Editor hinzufügen oder einen vorhandenen Ereignishandler mithilfe des [Ereignishandler-Assistenten](../ide/event-handler-wizard.md) für ein Dialogfeld-Steuerelement bearbeiten.

Sie können der Klasse, die das Dialogfeld implementiert, mithilfe des [Eigenschaftenfensters](/visualstudio/ide/reference/properties-window) ein Ereignis hinzufügen. Wenn Sie das Ereignis einer anderen Klasse hinzufügen möchten, verwenden Sie den Ereignishandler-Assistenten.

### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>So fügen Sie einem Dialogfeld-Steuerelement einen Ereignishandler hinzu

1. Führen Sie einen Doppelklick auf die Dialogfeldressource in der [Ressourcenansicht](../windows/resource-view-window.md) aus, um die Dialogfeldressource zu öffnen, die das Steuerelement im [Dialog-Editor](../windows/dialog-editor.md) enthält.

1. Klicken Sie mit der rechten Maustaste auf das Steuerelement aus, das das Benachrichtigungsereignis verarbeiten soll.

1. Klicken Sie im Kontextmenü auf **Ereignishandler hinzufügen**, um den Ereignishandler-Assistenten anzuzeigen.

1. Wählen Sie das Ereignis im Feld **Nachrichtentyp** aus, das der im Feld **Klassenliste** ausgewählten Klasse hinzugefügt werden soll.

1. Akzeptieren Sie den Standardnamen im Feld **Handlerfunktionsname**, oder geben Sie einen Namen Ihrer Wahl ein.

1. Klicken Sie auf **Hinzufügen und bearbeiten**, um den Ereignishandler dem Projekt hinzuzufügen und den Text-Editor bei der neuen Funktion zum Hinzufügen des entsprechenden Ereignishandlercodes zu öffnen.

   Wenn der ausgewählte Nachrichtentyp bereits über einen Ereignishandler für die ausgewählte Klasse verfügt, ist die Option **Hinzufügen und bearbeiten** nicht verfügbar, jedoch ist die Option **Code bearbeiten** verfügbar. Klicken Sie auf **Code bearbeiten**, um den Text-Editor bei der vorhandenen Funktion zu öffnen.

Alternativ können Sie Ereignishandler über das [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window) hinzufügen. Weitere Informationen finden Sie unter [Adding Event Handlers for Dialog Box Controls (Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente)](../windows/adding-event-handlers-for-dialog-box-controls.md).

## <a name="see-also"></a>Siehe auch

[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)<br>
[Adding a Member Variable (Hinzufügen einer Membervariablen)](../ide/adding-a-member-variable-visual-cpp.md)<br>
[Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)<br>
[MFC Message Handler (MFC-Meldungshandler)](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[Navigating the Class Structure (Navigieren in der Klassenstruktur)](../ide/navigating-the-class-structure-visual-cpp.md)