---
title: Befehle im Menü (C++)
ms.date: 02/15/2019
helpviewer_keywords:
- menu items, properties
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
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
ms.openlocfilehash: c9abf46907c473d4cf6d9e945038f70aa75bfc48
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026278"
---
# <a name="menu-commands-c"></a>Befehle im Menü (C++)

Die folgenden Informationen sind entsprechend so aufgebaut, dass die **Menü** Eigenschaften, die in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) bei der Auswahl eines Menübefehls. Diese sind alphabetisch aufgeführt, obwohl die **Eigenschaften** Fenster auch können Sie diese Eigenschaften nach Kategorie anzuzeigen.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|**Break**|Einer der folgenden Werte ist möglich:<br/>  - **Keine**: Kein Wechsel. Dies ist die Standardeinstellung.<br/>  - **Spalte**: Bei statischen Menüs bewirkt wird dieser Wert den Menübefehl in eine neue Zeile.<br/>      Bei Popupmenüs bewirkt dieser Wert, dass der Menübefehl in eine neue Spalte gesetzt wird, ohne dass zwischen den Spalten eine Trennlinie angezeigt wird.<br/>      Diese Eigenschaft wirkt sich nicht im Menü-Editor, sondern erst zur Laufzeit auf die Darstellung des Menüs aus.<br />   - **Bar**: Identisch mit **Spalte** außer dass bei Popupmenüs dieser Wert die neue Spalte von der alten Spalte getrennt durch eine vertikale Linie.<br/>      Diese Eigenschaft wirkt sich auf die Darstellung des Menüs nur zur Laufzeit nicht in der **Menü-Editor**.|
|**Beschriftung**|Text zur Beschreibung des Menübefehls (der Menüname). Einem der Buchstaben in der Beschriftung eines Menübefehls kann eine Zugriffstaste zugeordnet werden, indem ihm ein kaufmännisches Und-Zeichen (&) vorangestellt wird.|
|**Aktiviert**|Wenn **"true"**, der Menübefehl zu Beginn aktiviert ist. Typ: **Bool**. Standard: **"False"**.|
|**Aktiviert**|Wenn **FALSE**, ist das Menüelement deaktiviert.|
|**Grau**|Wenn **"true"**, ist der Menübefehl, Beginn grau dargestellt und inaktiv. Typ: **Bool**. Standard: **"False"**.|
|**Hilfe**|Richtet das Menüelement rechtsbündig aus. Standard: **"False"**.<br/><br/>Der Menübefehl für die **Hilfe** befindet sich beispielsweise in allen Windows-Anwendungen immer ganz rechts. Wenn Sie diese Eigenschaft für ein Menüelement festlegen, wird das Element ganz rechts am Ende des Menüs angezeigt. Bezieht sich auf Elemente des Hauptmenüs.|
|**ID**|Ein Symbol, das in der Headerdatei definiert ist. Typ: **Symbol**, **Ganzzahl**, oder **Zeichenfolge in Anführungszeichen**.<br/><br/>Sie können ein beliebiges Symbol verwenden, das üblicherweise in den Editoren verfügbar ist. Dies gilt auch, wenn das [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window) keine Dropdownliste enthält, aus der Sie auswählen können.|
|**Popup**|Wenn **"true"**, der Menübefehl ist ein Popup-Menü. Typ: **Bool**. Standard: **"True"** für Menüs der obersten Ebene in einer Menüleiste, andernfalls **"false"**.|
|**Eingabeaufforderung**|Enthält Text, der in der Statusleiste angezeigt werden soll, wenn dieser Menübefehl markiert wird. Der Text wird mit dem Bezeichner des Menübefehls in der Zeichenfolgentabelle gespeichert.<br/><br/>Diese Eigenschaft ist für jeden Projekttyp verfügbar, wobei die Laufzeitfunktionalität jedoch MFC-spezifisch ist.|
|**Rechtsbündig**|Richtet den Menübefehl auf der Menüleiste zur Laufzeit rechtsbündig aus. Typ: **Bool**. Standard: **"False"**.|
|**Von rechts nach links**|Ermöglicht die Darstellung der Menübefehle von rechts nach links, wenn die Benutzeroberfläche in eine Sprache übertragen werden soll, die von rechts nach links geschrieben wird, z. B. Hebräisch oder Arabisch.|
|**Trennzeichen**|Wenn **"true"**, der Menübefehl ein Trennzeichen ist. Typ: **Bool**. Standard: **"False"**.|

## <a name="associate-menu-commands"></a>Verknüpfen von Menübefehlen

Häufig ist es wünschenswert, dass ein Menübefehl und eine Tastenkombination den gleichen Programmbefehl ausgeben. Identische Befehle werden mithilfe der **Menü-Editor** auf den gleichen Ressourcenbezeichner des Menübefehls und ein Eintrag in der Zugriffstastentabelle Ihrer Anwendung zugewiesen. Anschließend bearbeiten Sie die [Beschriftung](../windows/menu-command-properties.md) des Menübefehls so, dass sie den Namen der Zugriffstaste anzeigt.

### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>So ordnen Sie einen Menübefehl einer Zugriffstaste zu

1. In der **Menü-Editor**, wählen Sie den gewünschten Menübefehl.

1. Fügen Sie im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)der Eigenschaft **Caption** den Namen der Zugriffstaste hinzu:

   - Geben Sie im Anschluss an die Menübeschriftung die Escapesequenz für einen Tabulator (\t) ein, damit alle Zugriffstasten des Menüs links ausgerichtet sind.

   - Geben Sie den Namen der Modifizierertaste (**STRG**, **Alt**, oder **UMSCHALT**) gefolgt von einem Pluszeichen (**+**) und den Namen, Buchstaben, oder Symbol der zusätzlichen Taste.

   Beispielsweise weisen **STRG**+**O** auf die **öffnen** Befehl die **Datei** im Menü Sie ändern, dass der Menübefehl  **Beschriftung** , damit sie wie folgt aussieht:

   ```
   &Open...\tCtrl+O
   ```

   Der Menübefehl in die **Menü-Editor** wird aktualisiert, um die neue Beschriftung so darzustellen, wie Sie es eingeben.

1. [Erstellen Sie den Zugriffstastentabellen-Eintrag](../windows/adding-an-entry-to-an-accelerator-table.md) im **Zugriffstasten** -Editor, und weisen Sie ihm den gleichen Bezeichner wie dem Menübefehl zu. Verwenden Sie eine Tastenkombination, die Ihrer Ansicht nach leicht zu merken ist.

Die MFC-Anwendung kann beschreibenden Text für jeden der Menübefehle im angezeigt, die ein Benutzer auswählen kann. Beschreibenden Text anzeigen, indem Sie eine Textzeichenfolge zuweisen, um jedem Menübefehl mit der **Eingabeaufforderung** -Eigenschaft in der **Eigenschaften** Fenster. Wenn eine Zeichenfolge in der [Zeichenfolgentabelle](../windows/string-editor.md) die gleiche ID wie der Befehl aufweist, zeigt eine MFC-Anwendung automatisch diese Zeichenfolgenressource in der Statusleiste der ausgeführten Anwendung an, wenn ein Benutzer auf ein Menüelement zeigt.

- Zum Zuordnen eines Menübefehls einer Statusleisten-Zeichenfolge in MFC-Anwendungen, in der **Menü-Editor**, wählen den Menübefehl aus. Geben Sie im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)den zugeordneten Statusleistentext im Feld **Eingabeaufforderung** ein.

In einem C++-Projekt können Sie eine Zugriffstaste (ein mnemonisches Zeichen, die dem Benutzer ermöglicht, wählen Sie im Menü mit der Tastatur) zuweisen, Ihren Menüs und Menübefehlen.

- Geben Sie einen Menübefehl eine Zugriffstaste (Tastenkombination) zuweisen möchten, ein kaufmännisches und-Zeichen (`&`) vor einen Buchstaben im Namen des Menüs oder Befehlsnamen, um diesen Buchstaben als die entsprechende Zugriffstaste festzulegen. 

   Z. B. "& Datei" legt **Alt**+**F** als Tastenkombination für den **Datei** Menü in Anwendungen für Microsoft Windows.

   Das Menüelement gibt einen sichtbaren Hinweis darauf, dass einem der Buchstaben eine Zugriffstaste zugeordnet ist. Der Buchstabe, der auf das kaufmännische Und-Zeichen folgt, wird unterstrichen dargestellt (abhängig vom Betriebssystem).

> [!NOTE]
> Stellen Sie sicher, dass alle Zugriffstasten in einem Menü eindeutig sind, indem Sie einen Rechtsklick auf das Menü und Auswahl **Mnemonik**.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Menü-Editor](../windows/menu-editor.md)<br/>

<!--
[Strings (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>-->