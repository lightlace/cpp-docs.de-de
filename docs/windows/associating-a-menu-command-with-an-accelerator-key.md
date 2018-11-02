---
title: Verknüpfen eines Menübefehls mit einer Zugriffstaste (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [C++], menu association
- commands [C++], associating menu commands with accelerator keys
- menu commands [C++], associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
ms.openlocfilehash: c68d391d1046ab1d1af2fcf54b43b25a7aa9a237
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478324"
---
# <a name="associating-a-menu-command-with-an-accelerator-key-c"></a>Verknüpfen eines Menübefehls mit einer Zugriffstaste (C++)

Häufig ist es wünschenswert, dass ein Menübefehl und eine Tastenkombination den gleichen Programmbefehl ausgeben. Verwenden Sie hierzu die **Menü** -Editor, um den gleichen Ressourcenbezeichner des Menübefehls und ein Eintrag in der Zugriffstastentabelle Ihrer Anwendung zugewiesen. Anschließend bearbeiten Sie die [Beschriftung](../windows/menu-command-properties.md) des Menübefehls so, dass sie den Namen der Zugriffstaste anzeigt.

### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>So ordnen Sie einen Menübefehl einer Zugriffstaste zu

1. Wählen Sie im **Menü** -Editor den gewünschten Menübefehl aus.

2. Fügen Sie im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)der Eigenschaft **Caption** den Namen der Zugriffstaste hinzu:

   - Geben Sie im Anschluss an die Menübeschriftung die Escapesequenz für einen Tabulator (\t) ein, damit alle Zugriffstasten des Menüs links ausgerichtet sind.

   - Geben Sie den Namen der Modifizierertaste (**STRG**, **Alt**, oder **UMSCHALT**) gefolgt von einem Pluszeichen (**+**) und den Namen, Buchstaben, oder Symbol der zusätzlichen Taste.

       Beispielsweise weisen **STRG**+**O** auf die **öffnen** Befehl die **Datei** im Menü Sie ändern, dass der Menübefehl  **Beschriftung** , damit sie wie folgt aussieht:

        ```
        &Open...\tCtrl+O
        ```

       Der Menübefehl in die **Menü** Editor wird aktualisiert, um die neue Beschriftung so darzustellen, wie Sie es eingeben.

3. [Erstellen Sie den Zugriffstastentabellen-Eintrag](../windows/adding-an-entry-to-an-accelerator-table.md) im **Zugriffstasten** -Editor, und weisen Sie ihm den gleichen Bezeichner wie dem Menübefehl zu. Verwenden Sie eine Tastenkombination, die Ihrer Ansicht nach leicht zu merken ist.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Hinzufügen von Befehlen zu einem Menü](../windows/adding-commands-to-a-menu.md)<br/>
[Menü-Editor](../windows/menu-editor.md)