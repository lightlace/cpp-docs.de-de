---
title: Bearbeiten mehrerer Menüs oder Menübefehle (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- menu commands [C++], selecting
- menus [C++], selecting
- commands [C++], menu commands
- commands [C++], copying on menus
- menu items, moving
- commands [C++], moving on menus
- menu items, copying
- menu items, deleting
- commands [C++], deleting from menus
- menus [C++], deleting
ms.assetid: b6f17897-2a40-4afd-97d4-a38b7661680b
ms.openlocfilehash: 45e2c4e97dc850b4d6fb13a5526911e4bd5caec2
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703219"
---
# <a name="editing-multiple-menus-or-menu-commands"></a>Bearbeiten mehrerer Menüs oder Menübefehle

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-select-multiple-menu-commands"></a>Auswählen mehrerer Menübefehle

Sie können mehrere Menünamen oder Menübefehle zum Ausführen von Massenvorgängen wie z. B. das Löschen oder Ändern der Eigenschaften auswählen.

Halten Sie die **STRG** Schlüssel, wählen Sie die Menüs oder Untermenübefehle werden sollen.

## <a name="to-move-and-copy-menus-and-menu-commands"></a>Zum Verschieben und Kopieren von Menüs und Menübefehlen

Sie können Menüs und Menübefehle mithilfe der Drag-and-Drop-Methode oder mithilfe von Befehlen im Kontextmenü (Rechtsklickmenü) verschieben oder kopieren.

### <a name="to-move-or-copy-menus-or-menu-commands-using-the-drag-and-drop-method"></a>So verschieben oder kopieren Sie Menüs oder Menübefehle mithilfe der Drag-and-Drop-Methode

1. Ziehen oder kopieren Sie das zu verschiebende Elemente in:

   - Eine neue Position im aktuellen Menü.

   - Ein anderes Menü. (Sie können zu anderen Menüs navigieren, indem Sie den Mauszeiger darüber ziehen.)

1. Legen Sie den Menübefehl ab, wenn die Einfügemarke die gewünschte Position anzeigt.

### <a name="to-move-or-copy-menus-or-menu-commands-using-shortcut-menu-commands"></a>So verschieben oder kopieren Sie Menübefehle mithilfe von Kontextmenübefehlen

1. Klicken Sie mit der rechten Maustaste auf mindestens ein Menü oder Menübefehl

1. Wählen Sie im Kontextmenü **Ausschneiden** (zum Verschieben) oder **Kopieren**aus.

1. Wenn Sie die Elemente zu einer anderen Menüressource verschieben, Ressource oder Ressourcenskriptdatei [öffnen Sie es in ein anderes Fenster](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

1. Wählen Sie die Position des Menüs oder Menübefehls aus, zu der Sie das Verschieben oder Kopieren vornehmen möchten.

1. Wählen Sie im Kontextmenü **Einfügen**aus. Das verschobene oder kopierte Element wird vor dem von Ihnen ausgewählten Element platziert.

   > [!NOTE]
   > Sie können Elemente auch ziehen und kopieren und sie in anderen Menüs in anderen Menüfenstern einfügen.

## <a name="to-delete-a-menu-or-menu-command"></a>So löschen Sie ein Menü oder einen Menübefehl

1. Klicken Sie mit der rechten Maustaste auf den Menünamen oder den Befehl.

1. Wählen Sie **Löschen** aus dem Kontextmenü.

   > [!NOTE]
   > Entsprechend können Sie mit dem Kontextmenü andere Aktionen ausführen, wie z. B. Kopieren, Ausschneiden, Einfügen, Neue einfügen, Trennzeichen einfügen, IDs bearbeiten, Als Popup anzeigen, Mnemonik überprüfen usw.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Menü-Editor](../windows/menu-editor.md)