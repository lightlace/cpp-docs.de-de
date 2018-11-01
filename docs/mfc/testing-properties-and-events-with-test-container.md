---
title: Testen der Eigenschaften und Ereignisse mit Testcontainer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b00eb755ef0fba0037df8c6d1e99bfd25d13b263
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078413"
---
# <a name="testing-properties-and-events-with-test-container"></a>Testen der Eigenschaften und Ereignisse mit Test Container

Die Test-Container-Anwendung, die im Lieferumfang von Visual C++ ist ein ActiveX-Steuerelementcontainer zum Testen und Debuggen von ActiveX-Steuerelemente. Testcontainer kann Entwickler des Steuerelements, um die Funktionalität des Steuerelements zu testen, indem Sie dessen Eigenschaften ändern, Aufrufen der Methoden und Ereignisse auslöst. Testcontainer kann Protokolle von Datenbindung Benachrichtigungen anzeigen und bietet auch Funktionen zum Testen der Funktionalität für die Persistenz eines ActiveX-Steuerelements: Sie können Eigenschaften in einen Stream oder Substorage speichern, sie erneut zu laden, und prüfen Sie die gespeicherten Daten. Dieser Abschnitt beschreibt, wie die grundlegenden Funktionen von Test-Container verwendet wird. Wählen Sie für Weitere Informationen die **Hilfe** Menü während der Ausführung des Test-Container.

### <a name="to-access-the-activex-control-test-container"></a>Auf den Testcontainer für ActiveX-Steuerelemente

1. Erstellen der [TSTCON-Beispiel: ActiveX-Steuerelementtestcontainer](../visual-cpp-samples.md).

### <a name="to-test-your-activex-control"></a>So testen Sie das ActiveX-Steuerelement

1. Auf der **bearbeiten** des Test-Container, klicken Sie anschließend auf **neues Steuerelement einfügen**.

1. In der **Steuerelement einfügen** Feld, wählen Sie das gewünschte Steuerelement aus, und klicken Sie auf **OK**. Das Steuerelement wird in der Steuerelement-Container angezeigt.

    > [!NOTE]
    >  Wenn das Steuerelement nicht, in aufgeführt ist der **Steuerelement einfügen** Dialogfeld stellen Sie sicher, dass Sie registriert haben sie mit der **Steuerelemente registrieren** Befehl die **Datei** Menü des Tests Container.

An diesem Punkt können Sie Eigenschaften oder Ereignisse des Steuerelements testen.

#### <a name="to-test-properties"></a>Um Eigenschaften zu testen.

1. Auf der **Steuerelement** Menü klicken Sie auf **Methoden aufrufen**.

1. In der **Methodenname** Dropdown-Liste, wählen Sie die PropPut-Methode für die Eigenschaft, die Sie testen möchten.

1. Ändern der **Parameterwert** oder **Parametertyp** und klicken Sie auf die **Wert festlegen** Schaltfläche.

1. Klicken Sie auf **Invoke** auf den neuen Wert auf das Objekt angewendet.

   Die Eigenschaft enthält jetzt den neuen Wert.

#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>Zum Testen von Ereignissen, und geben Sie das Ziel von Ereignisinformationen.

1. Auf der **Optionen** Menü klicken Sie auf **Protokollierung**.

1. Geben Sie das Ziel von Ereignisinformationen.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[Gewusst wie: Debuggen von ActiveX-Steuerelementen](/visualstudio/debugger/how-to-debug-an-activex-control)

