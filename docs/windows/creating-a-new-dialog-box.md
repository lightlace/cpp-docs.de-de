---
title: 'Vorgehensweise: Erstellen einer (Dialogfeld) (C++)'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog
helpviewer_keywords:
- dialog boxes [C++], creating
- Dialog Editor [C++], creating dialog boxes
- modal dialog boxes [C++], logon screens
- logon screens
- Test Dialog command
- testing, dialog boxes
- dialog boxes [C++], testing
- dialog boxes [C++], size
- dialog boxes [C++], positioning
ms.assetid: 303de801-c4f8-42e1-b622-353f6423f688
ms.openlocfilehash: c757c82978a5107374e6de2f8cff24319ed64f9c
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336474"
---
# <a name="how-to-create-a-dialog-box-c"></a>Vorgehensweise: Erstellen einer (Dialogfeld) (C++)

Die Position und Größe der einem C++-Dialogfeld, und die Position und Größe von Steuerelementen, werden in Dialogeinheiten gemessen. In der unteren rechten Ecke der Visual Studio Statusleiste an, wenn Sie sie auswählen, werden die Werte für einzelne Steuerelemente und das Dialogfeld angezeigt.

Beim Entwerfen ein Dialogfeld, können Sie auch simulieren und testen das Verhalten der Laufzeit ohne Ihr Programm kompilieren zu müssen. In diesem Modus können Sie folgende Aufgaben ausführen:

- Texteingabe, Auswahl aus Kombinationsfeldlisten, Aktivieren oder Deaktivieren von Optionen sowie Auswahl von Befehlen.

- Testen der Aktivierreihenfolge.

- Testen der Steuerelementgruppierung (z. B. von Optionsfeldern und Kontrollkästchen).

- Testen der Tastenkombinationen für Steuerelemente im Dialogfeld.

   > [!NOTE]
   > Verbindungen mit Dialogfeldcode, die mithilfe des Assistenten hergestellt wurden, sind nicht Teil der Simulation.

Während des Testverfahrens wird ein Dialogfeld normalerweise relativ zum Hauptprogrammfenster angezeigt. Wenn Sie des Dialogfelds festgelegt haben **Absolute Ausrichtung** Eigenschaft **"true"**, im Dialogfeld angezeigt, an der Position, die relativ zu der oberen linken Ecke des Bildschirms ist.

## <a name="to-create-a-new-dialog-box"></a>Um ein neues Dialogfeld zu erstellen.

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der **Ressource hinzufügen** wählen Sie im Dialogfeld **Dialogfeld** in die **Ressourcentyp** Liste aus, und wählen Sie dann **neu**.

   Wenn ein Pluszeichen (**+**) wird neben der **Dialogfeld** Ressourcentyp an, es bedeutet, dass Dialogfeldvorlagen verfügbar sind. Wählen Sie das Pluszeichen, um die Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und wählen **neu**.

   Das neue Dialogfeld wird geöffnet, der **Dialogfeld** Editor.

   Sie können auch [vorhandene Dialogfelder im Editor im Dialogfeld zur Bearbeitung öffnen](../windows/viewing-and-editing-resources-in-a-resource-editor.md).

## <a name="to-create-a-dialog-box-that-a-user-cant-exit"></a>Um ein Dialogfeld erstellen, die ein Benutzer nicht beendet werden kann

Sie können ein Laufzeitdialogfeld erstellen, die ein Benutzer nicht beendet werden kann. Diese Art Dialogfeld ist nützlich für Anmeldungen und für Sperren von Anwendungen oder Dokumenten.

1. Legen Sie im Abschnitt **Eigenschaften** des Dialogfelds die Eigenschaft **Systemmenü** auf **falsch**fest.

   Diese Einstellung das Systemmenü das Dialogfeld und **schließen** Schaltfläche.

1. Löschen Sie auf dem Formular des Dialogfelds die Schaltflächen **Abbrechen** und **OK** .

   Zur Laufzeit kann nicht beendet wird ein Benutzer ein modales Dialogfeld, das diese Eigenschaften aufweist.

Zum Testen dieser Art von Dialogfeld zu aktivieren, erkennt der Testfunktion für Dialogfeld Feld beim **Esc** gedrückt wird. (**Esc** ist auch bekannt als die virtuelle Taste "VK_ESCAPE".) Unabhängig davon, wie Sie das Dialogfeld zur Laufzeit Verhalten konzipiert ist, können Sie den Testmodus beenden, durch Drücken von **Esc**.

> [!NOTE]
> Für MFC-Anwendungen, um ein Dialogfeld erstellen, die Benutzer nicht beendet werden können, müssen Sie überschreiben das Standardverhalten des `OnOK` und `OnCancel` denn selbst wenn Sie die zugeordneten Schaltflächen löschen, das Dialogfeld immer noch durch Drücken von kann geschlossen werden  **Geben Sie** oder **Esc**.

## <a name="to-specify-the-location-and-size-of-a-dialog-box"></a>Die Position und Größe eines Dialogfelds angeben.

Es gibt drei Eigenschaften, die Sie, in festlegen können der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) angeben, in dem ein Dialogfeld, das auf dem Bildschirm angezeigt wird. Die **Center** Eigenschaft boolescher Wert; ist, wenn Sie den Wert auf **"true"**, das Dialogfeld wird immer in der Mitte des Bildschirms angezeigt. Wenn Sie die Einstellung **"false"**, Sie können dann Festlegen der **XPos** und **YPos** Eigenschaften explizit definieren, auf dem Bildschirm, das Dialogfeld wird angezeigt. Die Positionseigenschaften sind von Offsetwerten aus der linken oberen Ecke des Anzeigebereichs, die folgendermaßen definiert ist `{X=0, Y=0}`. Die Position basiert ebenfalls auf die **Absolute Ausrichtung** Eigenschaft: Wenn **"true"**, die Koordinaten sind relativ zum Bildschirm; Wenn **"false"**, die Koordinaten sind relativ zu das Dialogfeld " Fenster des Besitzers.

## <a name="to-test-a-dialog-box"></a>So testen Sie ein Dialogfeld

1. Wenn die **Dialogfeld** Editor wird das aktive Fenster, in der Menüleiste, wählen Sie **Format** > **Testdialogfeld**.

1. Um die Simulation zu beenden, drücken Sie die **Esc** oder wählen Sie die **schließen** -Schaltfläche in das Dialogfeld, das Sie testen.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Erstellen einer Ressource](../windows/how-to-create-a-resource.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Dialog-Editor](../windows/dialog-editor.md)<br/>
[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>