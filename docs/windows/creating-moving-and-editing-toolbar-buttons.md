---
title: Erstellen, verschieben und Bearbeiten von Symbolleistenschaltflächen (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.toolbar
helpviewer_keywords:
- buttons [C++], custom toolbars
- toolbar buttons [C++], editing
- buttons
- toolbar buttons [C++], creating
- Toolbar editor [C++], creating buttons
- toolbar buttons [C++], button image
- toolbar buttons [C++], creating
- toolbar buttons (in Toolbar editor)
- toolbar buttons [C++], moving
- Toolbar editor [C++], moving buttons
- Toolbar editor [C++], copying buttons
- toolbars [C++], copying buttons
- toolbar buttons [C++], copying
- toolbar buttons [C++], deleting
- Toolbar editor [C++], deleting buttons
- Toolbar editor [C++], spacing toolbar buttons
- toolbar buttons [C++], space between buttons
- toolbar controls [MFC], command ID
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- command IDs, toolbar buttons
- size, toolbar buttons
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- status bars [C++], active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: d0f0c6c6-9d7e-42b5-a86a-7558127386e7
ms.openlocfilehash: 2a67123e444ad208eaae74a24b72288f2dbb3bdb
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742699"
---
# <a name="creating-moving-and-editing-toolbar-buttons-c"></a>Erstellen, verschieben und Bearbeiten von Symbolleistenschaltflächen (C++)

Sie können ganz einfach erstellen, verschieben, kopieren und Bearbeiten von Symbolleistenschaltflächen.

Standardmäßig wird eine neue oder leere Schaltfläche am rechten Ende der Symbolleiste angezeigt. Sie können diese Schaltfläche, verschieben, bevor Sie ihn bearbeiten. Wenn Sie eine neue Schaltfläche erstellen, wird eine andere, leere Schaltfläche rechts neben der bearbeiteten Schaltfläche angezeigt. Wenn Sie eine Symbolleiste speichern, wird die Schaltfläche "leere" nicht gespeichert.

Die Eigenschaften einer Symbolleisten-Schaltfläche sind:

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|**ID**|Definiert die ID für die Schaltfläche. Die Dropdown-Liste enthält allgemeine **ID** Namen.|
|**Width**|Legt die Breite der Schaltfläche fest. 16 Pixel wird empfohlen.|
|**Height**|Legt die Höhe der Schaltfläche fest. Die Höhe einer Schaltfläche ändert sich die Höhe aller Schaltflächen auf der Symbolleiste. 15 Pixel wird empfohlen.|
|**Eingabeaufforderung**|Definiert die Nachricht in der Statusleiste angezeigt. Hinzufügen von \n und einen Namen hinzugefügt, Symbolleisten-Schaltfläche eine QuickInfo. Weitere Informationen finden Sie unter [Erstellen einer QuickInfo](../windows/creating-a-tool-tip-for-a-toolbar-button.md).|

**Breite** und **Höhe** gelten für alle Schaltflächen. Eine Bitmap, die zum Erstellen einer Symbolleiste verwendet wird, hat eine maximale Breite von 2048. Also, wenn Sie die Schaltflächenbreite auf 512 festlegen, können Sie nur vier Schaltflächen haben, und wenn Sie die Breite auf 513 festlegen, Sie können Sie nur drei Schaltflächen verwenden.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

Finden Sie die folgenden Aktionen aus:

## <a name="to-create-a-new-toolbar-button"></a>Erstellen Sie eine neue Symbolleisten-Schaltfläche

1. In [Ressourcenansicht](../windows/resource-view-window.md) erweitern Sie den Ressourcenordner (z. B. *Projekt1.rc*).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. Erweitern Sie die **Symbolleiste** Ordner, und wählen Sie eine Symbolleiste zur Bearbeitung.

1. Weisen Sie eine ID, auf die leere Schaltfläche am rechten Ende der Symbolleiste. Bearbeiten Sie dazu die **ID** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Beispielsweise empfiehlt es sich um einer Symbolleisten-Schaltfläche, die gleiche ID wie eine Menüoption gewähren. In diesem Fall verwenden Sie im Dropdown-Listenfeld auswählen der **ID** der Menüoption.

   - oder - 

   Wählen Sie die leere Schaltfläche am rechten Ende der Symbolleiste (in der **Symbolleiste anzeigen** Bereich) und Zeichnen zu beginnen. Die Befehls-ID eine Standard-Schaltfläche zugewiesen ist (ID_BUTTON\<n >).

Sie können auch kopieren und fügen Sie ein Image auf einer Symbolleiste als neue Schaltfläche.

## <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>Hinzufügen eines Bilds zu einer Symbolleiste als Schaltfläche

1. In [Ressourcenansicht](../windows/resource-view-window.md), öffnen Sie die Symbolleiste, indem Sie darauf doppelklicken.

1. Öffnen Sie als Nächstes das Bild, das Sie hinzufügen, klicken Sie auf der Symbolleiste möchten.

   > [!NOTE]
   > Wenn Sie das Bild in Visual Studio öffnen, öffnen sie in der **Image** Editor. Sie können das Bild auch in anderen Grafikprogrammen öffnen.

1. Von der **bearbeiten** Menü wählen **Kopie**.

1. Wechseln Sie durch Auswahl einer Registerkarte am oberen Rand der Datenquellen-Fenster auf der Symbolleiste.

1. Von der **bearbeiten** Menü wählen **einfügen**.

   Das Bild wird auf der Symbolleiste als neue Schaltfläche angezeigt.

## <a name="to-move-a-toolbar-button"></a>Verschieben eine Symbolleisten-Schaltfläche

In der **Symbolleiste anzeigen** Bereich, ziehen Sie die Schaltfläche, die Sie auf der Symbolleiste am neuen Speicherort verschieben möchten.

## <a name="to-copy-buttons-from-a-toolbar"></a>Zum Kopieren von Schaltflächen von einer Symbolleiste

1. Halten Sie die **STRG** Schlüssel.

1. In der **Symbolleiste anzeigen** Bereich, ziehen Sie die Schaltfläche mit den neuen Speicherort auf der Symbolleiste oder an einem Speicherort auf einer anderen Symbolleiste.

## <a name="to-delete-a-toolbar-button"></a>So löschen Sie eine Symbolleisten-Schaltfläche

Wählen Sie die Symbolleisten-Schaltfläche, und ziehen Sie es aus der Symbolleiste.

## <a name="to-insert-or-remove-space-between-buttons-on-a-toolbar"></a>Zum Einfügen oder Entfernen von Leerzeichen zwischen den Schaltflächen einer Symbolleiste

Im Allgemeinen um ein Leerzeichen zwischen den Schaltflächen einzufügen, ziehen Sie sie von anderen auf der Symbolleiste. Um Speicherplatz zu entfernen, ziehen Sie sie in Richtung gegenseitig aus.

### <a name="to-insert-a-space-before-a-button-that-isnt-followed-by-a-space"></a>Ein Leerzeichen vor eine Schaltfläche eingefügt, die gefolgt von einem Leerzeichen ist nicht

Ziehen Sie die Schaltfläche rechts oder nach unten Sie, bis sie die Schaltfläche "Weiter" während des laufenden Vorgangs zu überlappt.

### <a name="to-insert-a-space-before-a-button-that-is-followed-by-a-space-and-to-keep-the-trailing-space"></a>Ein Leerzeichen vor eine Schaltfläche eingefügt, die durch ein Leerzeichen folgt und der nachgestellte Leerzeichen zu halten.

Ziehen Sie die Schaltfläche aus, bis am rechten oder unteren Rand die Schaltfläche "Weiter Schaltflächenrand", oder geringfügig überlappt.

### <a name="to-insert-a-space-before-a-button-that-is-followed-by-a-space-and-close-up-that-following-space"></a>Fügen Sie ein Leerzeichen vor eine Schaltfläche, die durch ein Leerzeichen folgt, und schließen diese folgenden Speicherplatz

Ziehen Sie die Schaltfläche rechts oder nach unten Sie, bis sie die Schaltfläche "Weiter" während des laufenden Vorgangs zu überlappt.

### <a name="to-remove-a-space-between-buttons-on-a-toolbar"></a>So entfernen Sie ein Leerzeichen zwischen den Schaltflächen einer Symbolleiste

Ziehen Sie die Schaltfläche auf einer Seite des Speicherplatzes auf die Schaltfläche auf der anderen Seite für den Speicherplatz, bis sie die Schaltfläche "Weiter", etwa um die Hälfte überlappt.

   Wenn kein Platz im Zweifelsfall die Schaltfläche, die Sie ziehen ist aus, und Sie ziehen Sie die Schaltfläche mit den mehr als zur Hälfte hinter die benachbarte Schaltfläche der **Symbolleiste** Editor fügt auch ein Leerzeichen auf der entgegengesetzten Seite der Schaltfläche, die Sie durch Ziehen.

## <a name="to-change-the-properties-of-a-toolbar-button"></a>Zum Ändern der Eigenschaften einer Symbolleisten-Schaltfläche

1. Wählen Sie die Symbolleisten-Schaltfläche in einem C++-Projekt.

1. Geben Sie die neue ID in der **ID** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), oder verwenden Sie die Dropdownliste, wählen Sie ein neues **ID**.

## <a name="requirements"></a>Anforderungen

MFC oder ATL

## <a name="see-also"></a>Siehe auch

[Symbolleisten-Editor](../windows/toolbar-editor.md)
