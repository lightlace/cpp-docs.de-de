---
title: 'Vorgehensweise: Einfügen von Ressourcen zur Kompilierungszeit (C++)'
ms.date: 11/04/2016
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
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
ms.openlocfilehash: 52145d2a656a7cac0d07a43ceaf298fbebb5ad40
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55764076"
---
# <a name="how-to-include-resources-at-compile-time"></a>Vorgehensweise: Einfügen von Ressourcen zur Kompilierungszeit

Normalerweise ist es einfach und bequem, arbeiten mit der standardanordnung aller Ressourcen in einer Ressourcenskriptdatei (.rc). Aber Sie können Ressourcen hinzufügen in anderen Dateien zu Ihrem aktuellen Projekt zum Zeitpunkt der Kompilierung durch Auflisten der in der **Kompilierzeitdirektiven** im Feld der **Ressourcenincludes** Dialogfeld.

Es gibt verschiedene Gründe für das Platzieren von Ressourcen in einer Datei, die von der RC-Hauptdatei abweicht:

- Kommentare zu hinzufügen, das wird nicht gelöscht werden, wenn Sie die RC-Datei speichern.

   Die Ressourcen-Editoren nicht direkt gelesen RC oder `resource.h` Dateien. Der Ressourcencompiler kompiliert sie in .aps-Dateien, die von den Ressourcen-Editoren genutzt werden. Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten. Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind (z. B. Kommentare) ist während der Kompilierung verworfen. Sobald die .aps-Datei mit der RC-Datei nicht mehr synchron, die RC-Datei erneut generiert wird (Wenn Sie speichern, überschreibt der Ressourcen-Editor z. B. die RC-Datei und die `resource.h` Datei). Alle Änderungen an den Ressourcen selbst bleiben in der .rc-Datei, aber Kommentare gehen immer verloren, sobald die .rc-Datei überschrieben wird.

- Um die Ressourcen enthalten, die bereits entwickelt und getestet haben und keine weitere Änderung benötigen. (Alle Dateien, die sind enthalten, aber keine RC-Erweiterung wird nicht von der Ressourcen-Editor bearbeitet werden.)

- Zum Einbeziehen von Ressourcen, die durch mehrere unterschiedliche Projekte verwendet werden, oder die Teil einer Version-Quellcodeverwaltungssystem, und muss also vorhanden sein an einem zentralen Ort, in denen Änderungen auf alle Projekte auswirken.

- Zum Einbeziehen von Ressourcen (beispielsweise RCDATA-Ressourcen), die ein benutzerdefiniertes Format aufweisen. RCDATA-Ressourcen weisen möglicherweise spezielle Anforderungen auf. Beispielsweise können Sie einen Ausdruck für das Feld „nameID“ nicht als Wert verwenden. Finden Sie unter der Windows SDK-Dokumentation für Weitere Informationen.

Wenn Sie über Abschnitte in Ihren vorhandenen RC-Dateien, die eine der folgenden Bedingungen erfüllen verfügen, sollten Sie in den Abschnitten platzieren, in einem oder mehr getrennten RC-Datei, und beziehen Sie diese in Ihrem Projekt mithilfe der **Ressourcenincludes** Dialogfeld. Die *Projectname*RC2-Datei erstellt, die im Unterverzeichnis \res eines neuen Projekts für diesen Zweck verwendet wird.

Können Sie die **Ressourcenincludes** Dialogfeld in einem C++-Projekt so ändern Sie die normale arbeitsanordnung der Umgebung zum Speichern aller Ressourcen in der RC-Datei des Projekts und alle [Symbole](../windows/symbols-resource-identifiers.md) in Resource.h.

Zu öffnen der **Ressourcenincludes** klicken Sie im Dialogfeld mit der rechten Maustaste eine RC-Datei [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie dann **Ressourcenincludes** aus dem Kontextmenü. Dieses Dialogfeld enthält die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|---|---|
|**Symbolheaderdatei**|Erlaubt es Ihnen, den Namen der Headerdatei dort zu ändern, wo die Symboldefinitionen für Ihre Ressourcendatei gespeichert werden. Weitere Informationen finden Sie unter [ändern die Namen von Symbolheaderdateien](../windows/changing-the-names-of-symbol-header-files.md).|
|**Anweisungen für schreibgeschützte Symbole**|Ermöglicht Ihnen, Headerdateien einzufügen, die Symbole enthalten, die während einer bearbeitungssitzung sollte nicht geändert werden. Sie können z. B. eine Symboldatei einfügen, die von mehreren Projekten gemeinsam verwendet wird. Sie können auch die MFC H-Dateien einfügen. Weitere Informationen finden Sie unter [einschließlich gemeinsam genutzter (schreibgeschützter) oder berechneter Symbole](../windows/including-shared-read-only-or-calculated-symbols.md).|
|**Kompilierzeitdirektiven**|Können Sie Ressourcendateien einschließen, die erstellt und bearbeitet, separat von den Ressourcen in der Hauptressourcendatei, kompilierzeitanweisungen (z. B. diese Anweisungen, die bedingt Ressourcen einfügen) enthalten oder Ressourcen in einem benutzerdefinierten Format enthalten. Sie können auch der **Kompilierung Feld kompilierzeitanweisungen** zum standard-MFC-Ressourcendateien einzufügen. Weitere Informationen finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).|

> [!NOTE]
> Einträge in diesen Textfeldern angezeigt werden, in der RC-Datei markiert `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, und `TEXTINCLUDE 3` bzw. Weitere Informationen finden Sie unter [TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).

Nachdem Sie Änderungen, um Ihrer Ressourcendatei mithilfe vorgenommen haben der **Ressourcenincludes** im Dialogfeld müssen Sie die RC-Datei zu schließen und erneut öffnen, damit die Änderungen wirksam werden. Weitere Informationen finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in .NET Framework-Entwicklerhandbuch.

## <a name="to-include-resources-in-your-project-at-compile-time"></a>So beziehen Sie Ressourcen In Ihr Projekt zum Zeitpunkt der Kompilierung ein

1. Platzieren Sie die Ressourcen in einer Ressourcenskriptdatei mit einem eindeutigen Dateinamen. Verwenden Sie keine *Projectname*RC, weil der Dateiname für die Haupt-Ressourcenskriptdatei verwendet wird.

1. Mit der rechten Maustaste in der RC-Datei (in [Ressourcenansicht](../windows/resource-view-window.md)), und wählen Sie **Ressourcenincludes** aus dem Kontextmenü.

1. In der **Kompilierzeitdirektiven** hinzu, und die [#include](../preprocessor/hash-include-directive-c-cpp.md) Compilerdirektive, um die neue Ressourcendatei in der Hauptressourcendatei in der Entwicklungsumgebung enthalten.

   Die auf diese Weise in die Dateien einbezogenen Ressourcen werden zum Bestandteil Ihrer ausführbaren Datei zum Zeitpunkt der Kompilierung. Sie sind nicht für die Bearbeitung oder Änderung direkt zur Verfügung, wenn Sie auf die RC-Hauptdatei Datei des Projekts arbeiten. Öffnen Sie einbezogene RC-Dateien einzeln. Alle Dateien, die sind enthalten, aber keine RC-Erweiterung wird nicht von der Ressourcen-Editor bearbeitet werden.

## <a name="to-specify-include-directories-for-a-specific-resource-rc-file-c"></a>Angeben der Includeverzeichnisse für eine bestimmte Ressource (RC-Datei) (C++)

1. Mit der rechten Maustaste im Projektmappen-Explorer auf der RC-Datei, und wählen Sie **Eigenschaften** aus dem Kontextmenü.

1. In der **Eigenschaftenseiten** wählen Sie im Dialogfeld die **Ressourcen** Knoten im linken Bereich, geben Sie dann die zusätzlichen "include"-Verzeichnissen in die **Zusätzliche Includeverzeichnisse**Eigenschaft.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)<br/>
[Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)<br/>
