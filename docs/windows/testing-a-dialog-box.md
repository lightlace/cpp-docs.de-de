---
title: Entwerfen ein Dialogfeld (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes [C++], testing
- dialog boxes [C++], size
- dialog boxes [C++], positioning
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
ms.openlocfilehash: 4a879f6bb1cdcd4b4897e510fb21d04500dfd3f2
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742686"
---
# <a name="designing-a-dialog-box-c"></a>Entwerfen ein Dialogfeld (C++)

Die Position und Größe der einem C++-Dialogfeld, und die Position und Größe von Steuerelementen, werden in Dialogeinheiten gemessen. In der unteren rechten Ecke der Visual Studio Statusleiste an, wenn Sie sie auswählen, werden die Werte für einzelne Steuerelemente und das Dialogfeld angezeigt.

Beim Entwerfen ein Dialogfeld, können Sie auch simulieren und testen das Verhalten der Laufzeit ohne Ihr Programm kompilieren zu müssen. In diesem Modus können Sie folgende Aufgaben ausführen:

- Texteingabe, Auswahl aus Kombinationsfeldlisten, Aktivieren oder Deaktivieren von Optionen sowie Auswahl von Befehlen.

- Testen der Aktivierreihenfolge.

- Testen der Steuerelementgruppierung (z. B. von Optionsfeldern und Kontrollkästchen).

- Testen der Tastenkombinationen für Steuerelemente im Dialogfeld.

   > [!NOTE]
   > Verbindungen mit Dialogfeldcode, die mithilfe des Assistenten hergestellt wurden, sind nicht Teil der Simulation.

Während des Testverfahrens wird ein Dialogfeld normalerweise relativ zum Hauptprogrammfenster angezeigt. Wenn Sie des Dialogfelds festgelegt haben **Absolute Ausrichtung** Eigenschaft **"true"**, im Dialogfeld angezeigt, an der Position, die relativ zu der oberen linken Ecke des Bildschirms ist.

Weitere Informationen zur Vorgehensweise beim Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index).

## <a name="to-specify-the-location-and-size-of-a-dialog-box"></a>Die Position und Größe eines Dialogfelds angeben.

Es gibt drei Eigenschaften, die Sie, in festlegen können der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) angeben, in dem ein Dialogfeld, das auf dem Bildschirm angezeigt wird. Die **Center** Eigenschaft boolescher Wert; ist, wenn Sie den Wert auf **"true"**, das Dialogfeld wird immer in der Mitte des Bildschirms angezeigt. Wenn Sie die Einstellung **"false"**, Sie können dann Festlegen der **XPos** und **YPos** Eigenschaften explizit definieren, auf dem Bildschirm, das Dialogfeld wird angezeigt. Die Positionseigenschaften sind von Offsetwerten aus der linken oberen Ecke des Anzeigebereichs, die folgendermaßen definiert ist `{X=0, Y=0}`. Die Position basiert ebenfalls auf die **Absolute Ausrichtung** Eigenschaft: Wenn **"true"**, die Koordinaten sind relativ zum Bildschirm; Wenn **"false"**, die Koordinaten sind relativ zu das Dialogfeld " Fenster des Besitzers.

## <a name="to-test-a-dialog-box"></a>So testen Sie ein Dialogfeld

1. Wenn die **Dialogfeld** Editor wird das aktive Fenster, in der Menüleiste, wählen Sie **Format** > **Testdialogfeld**.

1. Um die Simulation zu beenden, drücken Sie **Esc**, oder wählen Sie einfach die **schließen** -Schaltfläche in das Dialogfeld, das Sie testen.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Dialog-Editor](../windows/dialog-editor.md)<br/>
[Ein- oder Ausblenden der Symbolleiste des Dialog-Editors](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)