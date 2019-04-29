---
title: Zeichenfolgen-Editor (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.string.F1
- vc.editors.string
helpviewer_keywords:
- String editor
- string tables
- string tables [C++], String editor
- string editing
- string editing, string tables
- resource editors [C++], String editor
- strings [C++], editing
- strings [C++], searching
- strings [C++]
- strings [C++], adding to string tables
- string tables [C++], deleting strings
- strings [C++], deleting in string tables
- string tables [C++], adding strings
- strings [C++], moving between files
- resource script files [C++], moving strings
- string editing, moving strings between resources
- String editor [C++], moving strings between files
- resource identifiers, string properties
- string tables [C++], changing strings
- strings [C++], properties
- String editor [C++], changing properties of multiple strings
- string tables [C++], changing caption of multiple strings
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
ms.openlocfilehash: 47d5835356863383b32baffc4475e01a652e9856
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387928"
---
# <a name="string-editor-c"></a>Zeichenfolgen-Editor (C++)

Eine Zeichenfolgentabelle in einer Windows-Ressource, die eine Liste mit IDs, Werten und Beschriftungen für alle Zeichenfolgen Ihrer Anwendung enthält. Beispielsweise befinden sich die Statusleistenmeldungen in der Zeichenfolgentabelle.

Beim Entwickeln einer Anwendung können Sie mehrere Zeichenfolgentabellen verwenden – eine für jede Sprache oder Bedingung. Ein ausführbares Moduls weist jedoch nur eine Zeichenfolgentabelle auf. Eine ausgeführte Anwendung kann auf verschiedene Zeichenfolgentabellen verweisen, wenn Sie die Tabellen in verschiedenen DLLs platzieren.

Mithilfe von Zeichenfolgentabellen können Sie Ihre Anwendung bequem in verschiedene Sprachen lokalisieren. Wenn sich alle Zeichenfolgen in einer Zeichenfolgentabelle befinden, können Sie die Anwendung lokalisieren, indem Sie die Zeichenfolgen (und andere Ressourcen) übersetzen, ohne den Quellcode zu ändern. Diese Situation ist sinnvoller, als manuell suchen und Ersetzen verschiedene Zeichenfolgen in Quelldateien enthalten.

> [!NOTE]
> Windows nicht die Erstellung leerer Zeichenfolgentabellen zu ermöglichen. Wenn Sie eine Zeichenfolgentabelle ohne Einträge erstellen, wird sie beim Speichern der Ressourcendatei automatisch gelöscht.

## <a name="how-to"></a>Gewusst wie

Die **Zeichenfolgen-Editor** können Sie:

### <a name="to-find-a-string-resource-in-the-string-table"></a>Um eine Zeichenfolgenressource in der Zeichenfolgentabelle zu finden.

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](how-to-create-a-resource-script-file.md#create-resources).

1. Wechseln Sie zum Menü **bearbeiten** > **suchen und Ersetzen** , und wählen Sie **finden**.

1. In der **Suchen nach** Feld, wählen Sie einen früheren Suchbegriff aus der Dropdown Liste aus, oder geben Sie die Beschriftung Text bzw. Ressourcenidentifizierer der Zeichenfolge gesucht werden soll.

1. Aktivieren Sie keines der **finden** Optionen, und wählen **Weitersuchen**.

> [!TIP]
> Mit [reguläre Ausdrücke](/visualstudio/ide/using-regular-expressions-in-visual-studio) bei der Suche in Dateien verwenden die **in Dateien suchen** -Befehl in der **bearbeiten** im Menü.
>
> Geben Sie einen regulären Ausdruck zum einem Muster entsprechen, oder wählen Sie die Schaltfläche rechts neben der **Suchen nach** Feld, um eine Liste von regulären Suchausdrücken anzuzeigen. Wenn Sie einen Ausdruck aus dieser Liste auswählen, wird dieser als Suchtext im der **Suchen nach** Feld.
>
> Wenn Sie reguläre Ausdrücke verwenden, werden Sie sicher, dass die **verwenden: Reguläre Ausdrücke** das Kontrollkästchen aktiviert ist.

### <a name="to-add-or-delete-a-string-resource"></a>Hinzufügen oder Löschen einer Zeichenfolgenressource

Sie können schnell einfügen oder Löschen von Einträgen in der Tabelle mit den **Zeichenfolgen-Editor**. Neue Zeichenfolgen befinden sich am Ende der Tabelle und den nächsten verfügbaren Bezeichner erhalten. Können Sie bearbeiten die **ID**, **Wert**, oder **Beschriftung** Eigenschaften in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) je nach Bedarf.

Die **Zeichenfolgen-Editor** stellt sicher, dass Sie keine ID, die bereits verwendet wird. Wenn Sie eine ID bereits verwendet wird, wählen Sie die **Zeichenfolgen-Editor** benachrichtigt wird, und weisen Sie eine generische eindeutige ID, z. B. `IDS_STRING58113`.

#### <a name="to-add-a-string-table-entry"></a>Zum Hinzufügen eines Eintrags der Zeichenfolge-Tabelle

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](how-to-create-a-resource-script-file.md#create-resources).

1. Mit der rechten Maustaste in der Tabelle, und wählen Sie **neue Zeichenfolge**.

1. In der **Zeichenfolgen-Editor**, wählen eine **ID** aus der **ID** Dropdown-Liste oder Eingabe ein *ID* direkt an Ort.

1. Bearbeiten der **Wert**, falls erforderlich.

1. Geben Sie einen Eintrag für die **Beschriftung**.

   > [!NOTE]
   > NULL-Zeichenfolgen, die in Windows-Zeichenfolgentabellen dürfen nicht. Wenn Sie einen Eintrag in der Zeichenfolgentabelle, die eine null-Zeichenfolge ist erstellen, erhalten Sie eine Meldung, die Sie auffordert, **Bitte geben Sie eine Zeichenfolge, die für diesen Tabelleneintrag**.

#### <a name="to-delete-a-string-table-entry"></a>So löschen Sie einen Zeichenfolgeneintrag-Tabelle

Wählen Sie den Eintrag, die, den Sie verwenden möchten, löschen, und führen Sie einen der folgenden:

- Wechseln Sie zum Menü **bearbeiten** > **löschen**.

- Mit der rechten Maustaste in der Zeichenfolge zu löschen, und wählen Sie **löschen**.

- Drücken Sie die **löschen** Schlüssel.

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Eine Zeichenfolge aus einer Ressource-Skriptdatei auf einen anderen zu verschieben.

1. [Öffnen Sie die Zeichenfolgentabellen in beide RC-Dateien](../windows/how-to-create-a-resource-script-file.md).

1. Mit der rechten Maustaste in der Zeichenfolge, um zu verschieben, und wählen Sie **Ausschneiden**.

1. Platzieren Sie den Cursor in der Ziel- **Zeichenfolgen-Editor** Fenster.

1. In der *RC* Datei, die Sie verschieben die Zeichenfolge, mit der rechten Maustaste, und wählen möchten **einfügen**.

> [!NOTE]
> Wenn die **ID** oder **Wert** der verschobenen Zeichenfolge Konflikte mit vorhandenen **ID** oder **Wert** in der Zieldatei, entweder diese **ID** oder **Wert** der verschobenen Zeichenfolge ändert.

### <a name="to-change-the-properties-of-a-string-resource"></a>Zum Ändern der Eigenschaften einer Ressource der Zeichenfolge

Sie können die direkte Bearbeitung verwenden, so ändern Sie die **ID**, **Wert**, und **Beschriftung** Eigenschaften.

> [!NOTE]
>  Sie können auch die Eigenschaften einer Zeichenfolge im Bearbeiten der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

#### <a name="to-change-a-string-or-its-identifier"></a>Eine Zeichenfolge oder den Bezeichner ändern.

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](how-to-create-a-resource-script-file.md#create-resources).

1. Wählen Sie die Zeichenfolge, die Sie verwenden möchten, bearbeiten, und doppelklicken Sie auf die **ID**, **Wert**, oder **Beschriftung** Spalte, Sie können:

   - Wählen Sie eine **ID** aus der **ID** Dropdown-Liste aus, oder geben eine *ID* direkt an Ort.

   - Geben Sie eine andere Zahl in die **Wert** Spalte.

   - Geben Sie die Änderungen in der **Beschriftung** Spalte.

#### <a name="to-change-the-caption-property-of-multiple-string-resources"></a>So ändern Sie die Caption-Eigenschaft von mehreren Zeichenfolgenressourcen

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](how-to-create-a-resource-script-file.md#create-resources).

1. Wählen Sie die Zeichenfolgen, die Sie ändern, indem Sie sie gedrückt halten, möchten die **STRG** gedrückt, während Sie jede auswählen.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), geben Sie einen neuen Wert für die Eigenschaft, die Sie ändern möchten.

1. Drücken Sie die **EINGABETASTE**.

### <a name="to-add-formatting-or-special-characters-to-a-string-resource"></a>Zum Hinzufügen von Formatierung oder Sonderzeichen zu einer Zeichenfolgenressource

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](how-to-create-a-resource-script-file.md#create-resources).

1. Wählen Sie die Zeichenfolge, die Sie ändern möchten.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), fügen Sie eine der standardmäßigen Escape-Sequenzen auf den Text im unten aufgeführten der **Beschriftung** ein und drücken Sie **EINGABETASTE**.

   |Um dies zu erhalten...|Geben Sie Folgendes aus...|
   |-----------------|---------------|
   | Zeilenwechsel | \\n |
   | Wagenrücklauf | \\r |
   | Registerkarte | \\t |
   | Umgekehrter Schrägstrich (\\) | \\\\ |
   | ASCII-Zeichen | \\Ddd (Oktalnotation) |
   | Warnung (Glocke) | \\a |

   > [!NOTE]
   > Die **Zeichenfolgen-Editor** unterstützt nicht den vollständigen Satz von ASCII-Zeichen in Escapezeichen. Sie können nur die oben aufgeführten verwenden.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)
<!--
[Strings](https://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)<br/>
[About Strings](/windows/desktop/menurc/about-strings)<br/>
[Customizing window layouts](/visualstudio/ide/customizing-window-layouts-in-visual-studio)-->