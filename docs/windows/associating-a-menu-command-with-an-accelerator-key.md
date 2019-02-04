---
title: Verknüpfen von Menübefehlen (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [C++], menu association
- commands [C++], associating menu commands with accelerator keys
- menu commands [C++], associating with keyboard shortcuts
- status bars [C++], associating menu items
- menus [C++], status bar text
- access keys [C++], checking
- menus [C++], shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics [C++], adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics [C++], uniqueness checking
- Check Mnemonics command
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
ms.openlocfilehash: f72fe5de3ef29b9575ef1a3138d4d114d7470fee
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703037"
---
# <a name="associating-menu-commands-c"></a>Verknüpfen von Menübefehlen (C++)

Häufig ist es wünschenswert, dass ein Menübefehl und eine Tastenkombination den gleichen Programmbefehl ausgeben. Identische Befehle werden mithilfe der **Menü** -Editor, um den gleichen Ressourcenbezeichner des Menübefehls und ein Eintrag in der Zugriffstastentabelle Ihrer Anwendung zugewiesen. Anschließend bearbeiten Sie die [Beschriftung](../windows/menu-command-properties.md) des Menübefehls so, dass sie den Namen der Zugriffstaste anzeigt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>So ordnen Sie einen Menübefehl einer Zugriffstaste zu

1. Wählen Sie im **Menü** -Editor den gewünschten Menübefehl aus.

1. Fügen Sie im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)der Eigenschaft **Caption** den Namen der Zugriffstaste hinzu:

   - Geben Sie im Anschluss an die Menübeschriftung die Escapesequenz für einen Tabulator (\t) ein, damit alle Zugriffstasten des Menüs links ausgerichtet sind.

   - Geben Sie den Namen der Modifizierertaste (**STRG**, **Alt**, oder **UMSCHALT**) gefolgt von einem Pluszeichen (**+**) und den Namen, Buchstaben, oder Symbol der zusätzlichen Taste.

       Beispielsweise weisen **STRG**+**O** auf die **öffnen** Befehl die **Datei** im Menü Sie ändern, dass der Menübefehl  **Beschriftung** , damit sie wie folgt aussieht:

        ```
        &Open...\tCtrl+O
        ```

       Der Menübefehl in die **Menü** Editor wird aktualisiert, um die neue Beschriftung so darzustellen, wie Sie es eingeben.

1. [Erstellen Sie den Zugriffstastentabellen-Eintrag](../windows/adding-an-entry-to-an-accelerator-table.md) im **Zugriffstasten** -Editor, und weisen Sie ihm den gleichen Bezeichner wie dem Menübefehl zu. Verwenden Sie eine Tastenkombination, die Ihrer Ansicht nach leicht zu merken ist.

## <a name="to-associate-a-menu-command-with-a-status-bar-text-string-in-mfc-applications"></a>Zuordnen ein Menübefehls mit einer Statusleisten-Zeichenfolge in MFC-Anwendungen

Die MFC-Anwendung kann beschreibenden Text für jeden der Menübefehle im angezeigt, die ein Benutzer auswählen kann. Beschreibenden Text anzeigen, indem Sie eine Textzeichenfolge zuweisen, um jedem Menübefehl mit der **Eingabeaufforderung** -Eigenschaft in der **Eigenschaften** Fenster. Wenn eine Zeichenfolge in der [Zeichenfolgentabelle](../windows/string-editor.md) die gleiche ID wie der Befehl aufweist, zeigt eine MFC-Anwendung automatisch diese Zeichenfolgenressource in der Statusleiste der ausgeführten Anwendung an, wenn ein Benutzer auf ein Menüelement zeigt.

1. Wählen Sie im **Menü** -Editor den Menübefehl aus.

1. Geben Sie im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)den zugeordneten Statusleistentext im Feld **Eingabeaufforderung** ein.

> [!NOTE]
> Diese Reihe von Schritten muss MFC.

## <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>So weisen Sie einem Menübefehl eine Zugriffstaste (Tastenkombination) zu

In einem C++-Projekt können Sie eine Zugriffstaste (ein mnemonisches Zeichen, die dem Benutzer ermöglicht, wählen Sie im Menü mit der Tastatur) zuweisen, Ihren Menüs und Menübefehlen.

Geben Sie ein kaufmännisches und-Zeichen (`&`) vor einen Buchstaben im Namen des Menüs oder Befehlsnamen, um diesen Buchstaben als die entsprechende Zugriffstaste festzulegen. Z. B. "& Datei" legt **Alt**+**F** als Tastenkombination für den **Datei** Menü in Anwendungen für Microsoft Windows.

   Das Menüelement gibt einen sichtbaren Hinweis darauf, dass einem der Buchstaben eine Zugriffstaste zugeordnet ist. Der Buchstabe, der auf das kaufmännische Und-Zeichen folgt, wird unterstrichen dargestellt (abhängig vom Betriebssystem).

   > [!NOTE]
   > Achten Sie darauf, dass alle Zugriffstasten in einem Menü eindeutig sind, indem Sie mit der rechten Maustaste auf das Menü klicken und im Kontextmenü **Mnemonik überprüfen** auswählen.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Menü-Editor](../windows/menu-editor.md)<br/>
[Hinzufügen von Befehlen zu einem Menü](../windows/adding-commands-to-a-menu.md)<br/>
[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
