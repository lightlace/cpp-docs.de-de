---
title: Ereignishandler-Assistent | Microsoft-Dokumentation
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
- Event Handler Wizard [C++]
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb3a025c293c3252b52b9ae705e6475b7095f049
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444098"
---
# <a name="event-handler-wizard"></a>Ereignishandler-Assistent

Dieser Assistent fügt einer beliebigen Klasse einen Ereignishandler für ein Dialogfeld-Steuerelement hinzu. Wenn Sie einen Ereignishandler über das [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window) hinzufügen, können Sie ihn nur der Klasse hinzufügen, die das Dialogfeld implementiert. Weitere Informationen finden Sie unter [Adding Event Handlers for Dialog Box Controls (Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente)](../windows/adding-event-handlers-for-dialog-box-controls.md).

- **Befehlsname**

   Identifiziert das ausgewählte Steuerelement, für das der Ereignishandler hinzugefügt wird. Dieses Feld ist nicht verfügbar.

- **Nachrichtentyp**

   Zeigt die Liste der aktuell verfügbaren Meldungshandler für das ausgewählte Steuerelement an.

- **Handlerfunktionsname**

   Zeigt den Namen der Funktion an, die zur Behandlung des Ereignisses hinzugefügt wird. Der Name basiert standardmäßig auf dem Nachrichtentyp und dem Befehl, und „On“ wird vorangestellt. Beispielsweise zeigt der Nachrichtentyp `BN_CLICKED` für die Schaltfläche namens `IDC_BUTTON1` den Handlerfunktionsnamen `OnBnClickedButton1` an.

- **Klassenliste**

   Zeigt die verfügbaren Klassen an, denen Sie einen Ereignishandler hinzufügen können. Die Klasse für das ausgewählte Dialogfeld wird rot angezeigt.

- **Handlerbeschreibung**

   Gibt eine Beschreibung für das im Feld **Nachrichtentyp** ausgewählte Element an. Dieses Feld ist nicht verfügbar.

- **Hinzufügen und Bearbeiten**

   Fügt der ausgewählten Klasse oder dem Objekt den Meldungshandler hinzu, und öffnet dann den Text-Editor bei der neuen Funktion, damit Sie den Handlercode für Benachrichtigungen des Steuerelements hinzufügen können.

- **Code bearbeiten**

   Öffnet den Text-Editor bei der ausgewählten vorhandenen Funktion, damit Sie den Handlercode für Benachrichtigungen des Steuerelements hinzufügen oder bearbeiten können.

## <a name="see-also"></a>Siehe auch

[Adding an Event Handler (Hinzufügen eines Ereignishandlers)](../ide/adding-an-event-handler-visual-cpp.md)