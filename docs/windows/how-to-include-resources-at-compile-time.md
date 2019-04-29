---
title: 'Vorgehensweise: Einfügen von Ressourcen zur Kompilierungszeit (C++)'
ms.date: 02/14/2019
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
- vc.editors.resourceincludes
helpviewer_keywords:
- comments [C++], compiled files
- resources [C++], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
- Resource Includes dialog box [C++]
- rc files [C++], changing storage
- symbol header files [C++], changing
- .rc files [C++], changing storage
- symbol header files [C++], read-only
- symbols [C++], symbol header files
- directories [C++], specifying include paths for resources
- include files [C++], specifying for resources
- resources [C++], including in projects
- symbols [C++], finding
- resources [C++], searching for symbols
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
ms.openlocfilehash: ca24a10f905e61feb2b090ba3966c752db3d4444
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350922"
---
# <a name="how-to-include-resources-at-compile-time-c"></a>Vorgehensweise: Einfügen von Ressourcen zur Kompilierungszeit (C++)

Standardmäßig alle Ressourcen in einer Ressourcenskriptdatei (.rc) befinden, aber es gibt viele Gründe, um Ressourcen in einer Datei, die wichtigsten RC-Datei erstellt werden:

- Kommentare zu hinzufügen, das wird nicht gelöscht werden, wenn Sie die RC-Datei speichern.

- Um die Ressourcen enthalten, die bereits entwickelt und getestet haben und keine weitere Änderung benötigen. Alle Dateien, die sind enthalten, aber keine RC-Erweiterung wird nicht von der Ressourcen-Editor bearbeitet werden.

- Zum Einbeziehen von Ressourcen, die von verschiedenen Projekten verwendet werden, oder, die sich in einer Version-Quellcodeverwaltungssystem. Diese Ressourcen müssen an einem zentralen Ort vorhanden sein, in denen Änderungen auf alle Projekte auswirken.

- Zum Einbeziehen von Ressourcen (z. B. RCDATA-Ressourcen), die ein benutzerdefiniertes Format sind. RCDATA-Ressourcen haben besondere Anforderungen, die Sie nicht möglich, in einen Ausdruck, als Wert für verwenden die `nameID` Feld.

Wenn Sie über Abschnitte in Ihren vorhandenen RC-Dateien, die eine der folgenden Bedingungen erfüllen verfügen, platzieren Sie diese Abschnitte auf eine oder mehrere RC-Dateien zu trennen, und beziehen Sie diese in Ihrem Projekt mithilfe der **Ressourcenincludes** Dialogfeld.

## <a name="resource-includes"></a>Ressourcenincludes

Sie können Ressourcen hinzufügen von anderen Dateien zu Ihrem Projekt zum Zeitpunkt der Kompilierung durch Auflisten der in der **Kompilierzeitdirektiven** im Feld der **Ressourcenincludes** Dialogfeld. Verwenden der **Ressourcenincludes** Dialogfeld so ändern Sie die normale arbeitsanordnung der Umgebung des Projekts zum Speichern aller Ressourcen in der RC-Datei des Projekts und alle [Symbole](../windows/symbols-resource-identifiers.md) in `Resource.h`.

Öffnen Sie zum Einstieg die **Ressourcenincludes** mit der rechten Maustaste einer RC-Datei in das Dialogfeld [Ressourcenansicht](how-to-create-a-resource-script-file.md#create-resources), wählen **Ressourcenincludes** und notieren Sie die folgenden Eigenschaften:

| Eigenschaft | Beschreibung |
|---|---|
| **Symbolheaderdatei** | Können Sie den Namen der Headerdatei ändern, wo die Symboldefinitionen für Ihre Ressourcendateien gespeichert werden.<br/><br/>Weitere Informationen finden Sie unter [ändern die Namen von Symbolheaderdateien](../windows/changing-the-names-of-symbol-header-files.md). |
| **Anweisungen für schreibgeschützte Symbole** | Ermöglicht Ihnen, Headerdateien einzufügen, die Symbole enthalten, die sollte nicht geändert werden.<br/><br/>Beispielsweise Symboldateien für andere Projekte freigegeben werden. Dies kann auch die MFC h-Dateien enthalten. Weitere Informationen finden Sie unter [einschließlich gemeinsam genutzter (schreibgeschützter) oder berechneter Symbole](../windows/including-shared-read-only-or-calculated-symbols.md). |
| **Kompilierzeitdirektiven** | Können Sie Ressourcendateien einschließen, die erstellt und bearbeitet, separat von den Ressourcen in der Hauptressourcendatei, kompilierzeitanweisungen (z. B. diese Anweisungen, die bedingt Ressourcen einfügen) enthalten oder Ressourcen in einem benutzerdefinierten Format enthalten.<br/><br/>Sie können auch der **Kompilierung Feld kompilierzeitanweisungen** zum standard-MFC-Ressourcendateien einzufügen. |

> [!NOTE]
> Einträge in diesen Textfeldern angezeigt werden, in der RC-Datei markiert `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, und `TEXTINCLUDE 3` bzw. Weitere Informationen finden Sie unter [TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).

Sobald Änderungen an Ihrer Ressourcendatei mithilfe vorgenommen werden die **Ressourcenincludes** (Dialogfeld), müssen Sie schließen und erneut die *RC* -Datei für die Änderungen wirksam werden.

### <a name="to-include-resources-in-your-project-at-compile-time"></a>So beziehen Sie Ressourcen In Ihr Projekt zum Zeitpunkt der Kompilierung ein

1. Platzieren Sie die Ressourcen in einer Ressourcenskriptdatei mit einem eindeutigen Dateinamen. Verwenden Sie keine *projectname.rc*, da dies der Name der für die Haupt-Ressourcenskriptdatei verwendeten Datei ist.

1. Mit der rechten Maustaste die *RC* Datei [Ressourcenansicht](how-to-create-a-resource-script-file.md#create-resources) , und wählen Sie **Ressourcenincludes**.

1. In der **Kompilierzeitdirektiven** hinzu, und die [#include](../preprocessor/hash-include-directive-c-cpp.md) Compilerdirektive, um die neue Ressourcendatei in der Hauptressourcendatei in der Entwicklungsumgebung enthalten.

Die Ressourcen in Dateien auf diese Weise erfolgen nur Teil der ausführbaren Datei zum Zeitpunkt der Kompilierung und nicht zur Verfügung, für die Bearbeitung oder Änderung, wenn Sie auf die RC-Hauptdatei Datei des Projekts arbeiten. Einbezogene RC-Dateien müssen separat geöffnet werden, und alle Dateien enthalten, ohne die RC-Erweiterung werden nicht auf der Ressourcen-Editor bearbeitet werden.

### <a name="to-specify-include-directories-for-a-specific-resource-rc-file"></a>Angeben der Includeverzeichnisse für eine bestimmte Ressourcendatei (.rc)

1. Mit der rechten Maustaste die *RC* Datei **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**.

1. Wählen Sie die **Ressourcen** im linken Bereich den Knoten, und geben Sie Zusätzliche Includeverzeichnisse der **Zusätzliche Includeverzeichnisse** Eigenschaft.

### <a name="to-find-symbols-in-resources"></a>So suchen Sie Symbole in Ressourcen

1. Wechseln Sie zum Menü **bearbeiten** > [Suchsymbol](/visualstudio/ide/go-to).

   > [!TIP]
   > Mit [reguläre Ausdrücke](/visualstudio/ide/using-regular-expressions-in-visual-studio) wählen Sie in den Suchergebnissen [in Dateien suchen](/visualstudio/ide/reference/find-command) in die **bearbeiten** Menü anstelle von **Suchsymbol**. Wählen Sie die **verwenden: Reguläre Ausdrücke** Kontrollkästchen in der [suchen (Dialogfeld)](/visualstudio/ide/finding-and-replacing-text) und klicken Sie in der **Suchen nach** Feld können Sie einen Suche mit regulären Ausdruck aus der Dropdown-Liste. Wenn Sie einen Ausdruck aus dieser Liste auswählen, wird dieser als Suchtext im der **Suchen nach** Feld.

1. In der **Suchen nach** Feld, wählen Sie einen früheren Suchbegriff aus der Dropdown-Liste aus, oder geben Sie die Zugriffstaste, die Sie suchen z. B., möchten `ID_ACCEL1`.

1. Aktivieren Sie keines der **finden** "Optionen", und wählen Sie **Weitersuchen**.

> [!NOTE]
> Die Suche nach Symbolen in Zeichenfolgen-, Zugriffstasten- oder Binärressourcen wird nicht unterstützt.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Vorgehensweise: Ressourcen erstellen](../windows/how-to-create-a-resource-script-file.md)<br/>
[Vorgehensweise: Ressourcen verwalten](../windows/how-to-copy-resources.md)<br/>