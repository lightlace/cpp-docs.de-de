---
title: Zeichenfolgen-Editor (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: 24e4e6ba5b9c2dff1a179bea39830f4a3bbe5879
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702976"
---
# <a name="string-editor-c"></a>Zeichenfolgen-Editor (C++)

Eine Zeichenfolgentabelle in einer Windows-Ressource, die eine Liste mit IDs, Werten und Beschriftungen für alle Zeichenfolgen Ihrer Anwendung enthält. Beispielsweise befinden sich die Statusleistenmeldungen in der Zeichenfolgentabelle.

Beim Entwickeln einer Anwendung können Sie mehrere Zeichenfolgentabellen verwenden – eine für jede Sprache oder Bedingung. Ein ausführbares Moduls weist jedoch nur eine Zeichenfolgentabelle auf. Eine ausgeführte Anwendung kann auf verschiedene Zeichenfolgentabellen verweisen, wenn Sie die Tabellen in verschiedenen DLLs platzieren.

Mithilfe von Zeichenfolgentabellen können Sie Ihre Anwendung bequem in verschiedene Sprachen lokalisieren. Wenn sich alle Zeichenfolgen in einer Zeichenfolgentabelle befinden, können Sie die Anwendung lokalisieren, indem Sie die Zeichenfolgen (und andere Ressourcen) übersetzen, ohne den Quellcode zu ändern. Diese Situation ist sinnvoller, als manuell suchen und Ersetzen verschiedene Zeichenfolgen in Quelldateien enthalten.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (Projekte, die die common Language Runtime als Ziel), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

Verwenden der **Zeichenfolge** -Editor für die folgenden Aktionen:

## <a name="to-find-a-string-resource-in-the-string-table"></a>Um eine Zeichenfolgenressource in der Zeichenfolgentabelle zu finden.

Sie können eine oder mehrere Zeichenfolgen in der Zeichenfolgentabelle suchen und verwenden Sie [reguläre Ausdrücke](/visualstudio/ide/using-regular-expressions-in-visual-studio) mit der **in Dateien suchen** Befehl (**bearbeiten** Menü), suchen Sie alle Vorkommnisse von Zeichenfolgen die einem Muster entsprechen.

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. Auf der **bearbeiten** , wählen Sie im Menü **suchen und Ersetzen**, wählen Sie dann **finden**.

1. In der **Suchen nach** Feld, wählen Sie einen früheren Suchbegriff aus der Dropdown-Liste aus, oder geben Sie die Beschriftung Text bzw. Ressourcenidentifizierer der Zeichenfolge gesucht werden soll.

1. Aktivieren Sie keines der **finden** Optionen.

1. Wählen Sie **Weitersuchen**.

   > [!TIP]
   > Verwenden Sie zum Verwenden von regulärer Ausdrücken beim Durchsuchen von Dateien die **in Dateien suchen** Befehl. Geben Sie einen regulären Ausdruck zum einem Muster entsprechen, oder wählen Sie die Schaltfläche rechts neben der **Suchen nach** Feld, um eine Liste von regulären Suchausdrücken anzuzeigen. Wenn Sie einen Ausdruck aus dieser Liste auswählen, wird dieser als Suchtext im der **Suchen nach** Feld. Wenn Sie reguläre Ausdrücke verwenden, werden Sie sicher, dass die **verwenden: Reguläre Ausdrücke** das Kontrollkästchen aktiviert ist.

## <a name="to-add-or-delete-a-string-resource"></a>Hinzufügen oder Löschen einer Zeichenfolgenressource

Sie können schnell einfügen oder Löschen von Einträgen in der Tabelle mit den **Zeichenfolge** Editor. Neue Zeichenfolgen befinden sich am Ende der Tabelle und den nächsten verfügbaren Bezeichner erhalten. Anschließend können Sie bearbeiten die **ID**, **Wert**, oder **Beschriftung** Eigenschaften in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) je nach Bedarf.

Die **Zeichenfolge** Editor stellt sicher, dass Sie keine ID, die bereits verwendet wird. Wenn Sie eine ID bereits verwendet wird, wählen Sie die **Zeichenfolge** Editor benachrichtigt wird, und weisen Sie eine generische eindeutige ID, z. B. `IDS_STRING58113`.

### <a name="to-add-a-string-table-entry"></a>Zum Hinzufügen eines Eintrags der Zeichenfolge-Tabelle

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. Mit der rechten Maustaste in der Tabelle, und wählen Sie **neue Zeichenfolge** aus dem Kontextmenü.

1. In der **Zeichenfolge** -Editor, wählen eine **ID** aus der ID Dropdown-Liste oder geben Sie eine ID direkt vorhanden.

1. Bearbeiten der **Wert**, falls erforderlich.

1. Geben Sie einen Eintrag für die **Beschriftung**.

   > [!NOTE]
   > NULL-Zeichenfolgen werden in der Windows-Zeichenfolgentabellen nicht zulässig. Wenn Sie einen Eintrag in der Zeichenfolgentabelle, die eine null-Zeichenfolge ist erstellen, erhalten Sie eine Meldung gebeten, "Bitte geben Sie eine Zeichenfolge für diesen Tabelleneintrag."

### <a name="to-delete-a-string-table-entry"></a>So löschen Sie einen Zeichenfolgeneintrag-Tabelle

1. Wählen Sie den zu löschenden Eintrag aus.

1. Auf der **bearbeiten** , wählen Sie im Menü **löschen**.

\- oder –

 Mit der rechten Maustaste in der Zeichenfolge, die Sie verwenden möchten, löschen, und wählen **löschen** aus dem Kontextmenü.

\- oder –

 Drücken Sie die **löschen** Schlüssel.

## <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Eine Zeichenfolge aus einer Ressource-Skriptdatei auf einen anderen zu verschieben.

1. Öffnen Sie die Zeichenfolgentabellen in beide RC-Dateien ein. (Weitere Informationen finden Sie unter [Anzeigen von Ressourcen eine Ressource außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. Mit der rechten Maustaste in der Zeichenfolge, die Sie verschieben möchten und wählen Sie **Ausschneiden** aus dem Kontextmenü.

1. Platzieren Sie den Cursor in der Ziel- **Zeichenfolgen-Editor** Fenster.

1. In der RC-Datei in das Sie verschieben, die Zeichenfolge möchten, mit der Maustaste, und wählen Sie **einfügen** aus dem Kontextmenü.

   > [!NOTE]
   > Wenn die **ID** oder **Wert** der verschobenen Zeichenfolge Konflikte mit vorhandenen **ID** oder **Wert** in der Zieldatei, entweder die **ID** oder **Wert** der verschobenen Zeichenfolge ändert. Wenn eine Zeichenfolge mit dem gleichen vorhanden ist **ID**, **ID** der verschobenen Zeichenfolge ändert. Wenn eine Zeichenfolge mit dem gleichen vorhanden ist **Wert**, **Wert** der verschobenen Zeichenfolge ändert.

## <a name="to-change-the-properties-of-a-string-resource"></a>Zum Ändern der Eigenschaften einer Ressource der Zeichenfolge

Sie können die direkte Bearbeitung verwenden, so ändern Sie die ID-Wert und Beschriftungseigenschaften.

### <a name="to-change-a-string-or-its-identifier"></a>Eine Zeichenfolge oder den Bezeichner ändern.

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Wählen Sie die Zeichenfolge, die Sie bearbeiten möchten, und doppelklicken Sie auf die **ID**, **Wert**, oder **Beschriftung** Spalte. Sie können jetzt:

   - Wählen Sie eine **ID** aus der **ID Dropdown-** Liste oder Eingabe ein `ID` direkt an Ort.

   - Geben Sie eine andere Zahl in die **Wert** Spalte.

   - Geben Sie die Änderungen in der **Beschriftung** Spalte.

        > [!NOTE]
        >  Sie können auch die Eigenschaften einer Zeichenfolge im Bearbeiten der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

### <a name="to-change-the-caption-property-of-multiple-string-resources"></a>So ändern Sie die Caption-Eigenschaft von mehreren Zeichenfolgenressourcen

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. Wählen Sie die Zeichenfolgen, die Sie ändern, indem Sie sie gedrückt halten, möchten die **STRG** gedrückt, während Sie jede auswählen.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), geben Sie einen neuen Wert für die Eigenschaft, die Sie ändern möchten.

1. Drücken Sie die **EINGABETASTE**.

## <a name="to-add-formatting-or-special-characters-to-a-string-resource"></a>Zum Hinzufügen von Formatierung oder Sonderzeichen zu einer Zeichenfolgenressource

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. Wählen Sie die Zeichenfolge, die Sie ändern möchten.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), fügen Sie eine der standardmäßigen Escape-Sequenzen auf den Text im unten aufgeführten der **Beschriftung** Feld, und drücken Sie **EINGABETASTE**.

   |Um dies zu erhalten.|Geben Sie Folgendes|
   |-----------------|---------------|
   | Zeilenwechsel | \\n |
   | Wagenrücklauf | \\r |
   | Registerkarte | \\t |
   | Umgekehrter Schrägstrich (\\) | \\\\ |
   | ASCII-Zeichen | \\Ddd (Oktalnotation) |
   | Warnung (Glocke) | \\a |

> [!NOTE]
> Die **Zeichenfolge** -Editor unterstützt nicht den vollständigen Satz von ASCII-Zeichen in Escapezeichen. Sie können nur die oben aufgeführten verwenden.

> [!NOTE]
> Windows erlaubt die Erstellung leerer Zeichenfolgentabellen nicht. Wenn Sie eine Zeichenfolgentabelle ohne Einträge erstellen, wird sie beim Speichern der Ressourcendatei automatisch gelöscht.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Zeichenfolgen](https://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)<br/>
[Informationen über Zeichenfolgen](/windows/desktop/menurc/about-strings)<br/>
[Anpassen von Fensterlayouts](/visualstudio/ide/customizing-window-layouts-in-visual-studio)