---
title: Testen eines Dialogfelds (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes [C++], testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
ms.openlocfilehash: 101a2b556b2593953bfa6482f96d5b1aadc38d1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625064"
---
# <a name="testing-a-dialog-box-c"></a>Testen eines Dialogfelds (C++)

Beim Entwerfen eines Dialogfelds können Sie dessen Laufzeitverhalten simulieren und testen, ohne das Programm zu kompilieren. In diesem Modus können Sie folgende Aufgaben ausführen:

- Texteingabe, Auswahl aus Kombinationsfeldlisten, Aktivieren oder Deaktivieren von Optionen sowie Auswahl von Befehlen.

- Testen der Aktivierreihenfolge.

- Testen der Steuerelementgruppierung (z. B. von Optionsfeldern und Kontrollkästchen).

- Testen der Tastenkombinationen für Steuerelemente im Dialogfeld.

   > [!NOTE]
   > Verbindungen mit Dialogfeldcode, die mithilfe des Assistenten hergestellt wurden, sind nicht Teil der Simulation.

Während des Testverfahrens wird ein Dialogfeld normalerweise relativ zum Hauptprogrammfenster angezeigt. Wenn Sie des Dialogfelds festgelegt haben **Absolute Ausrichtung** Eigenschaft **"true"**, im Dialogfeld angezeigt, an der Position, die relativ zu der oberen linken Ecke des Bildschirms ist.

### <a name="to-test-a-dialog-box"></a>So testen Sie ein Dialogfeld

1. Wenn die **Dialogfeld** Editor wird das aktive Fenster, in der Menüleiste, wählen Sie **Format** > **Testdialogfeld**.

2. Um die Simulation zu beenden, drücken Sie die **Esc**, oder wählen Sie einfach die **schließen** Schaltfläche im Dialogfeld für die Tests.

Weitere Informationen zur Vorgehensweise beim Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Dialog-Editor](../windows/dialog-editor.md)<br/>
[Ein- oder Ausblenden der Symbolleiste des Dialog-Editors](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)