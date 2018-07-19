---
title: Eigenschaftenseiten (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.NotAProp.Edit
dev_langs:
- C++
helpviewer_keywords:
- project-file macro
- project properties [C++], default values
- user-defined values
- project properties [C++], setting
- macros, project-file
- property pages, project settings
- Visual C++ projects, properties
- build macro
- user-defined macros
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1dc831dff6d1e3dbef4fc762712e8125a5b20e1
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33339708"
---
# <a name="property-pages-visual-c"></a>Eigenschaftenseiten (Visual C++)

Mithilfe von Eigenschaftenseiten können Sie Einstellungen für Visual Studio-Projekte angeben. Klicken Sie zum Öffnen des Dialogfelds **Eigenschaftenseiten** für ein Visual Studio-Projekt im Menü **Projekt** auf **Eigenschaften**.

Sie können Projekteinstellungen angeben, damit sie alle Buildkonfigurationen übernehmen. Alternativ können Sie unterschiedliche Projekteigenschaften für jede Buildkonfiguration angeben. Beispielsweise können Sie bestimmte Einstellungen für die Releasekonfiguration und andere Einstellungen für die Debugkonfiguration festlegen.

Es werden nicht alle verfügbaren Seiten zwangsläufig im Dialogfeld **Eigenschaftenseiten** angezeigt. Welche Seiten angezeigt werden, hängt von den Dateitypen im Projekt ab.

Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).

Informationen zu Projekten unter anderen Betriebssystemen als Windows finden Sie unter [Referenz zur Linux C++-Eigenschaftenseite](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->.

## <a name="default-properties-vs-modified-properties"></a>Standardeigenschaften im Vergleich mit geänderten Eigenschaften

Beim Verwenden des Dialogfelds **Neues Projekt** zum Erstellen eines Projekts verwendet Visual Studio die angegebene Projektvorlage, um die Projekteigenschaften zu initialisieren. Daher können die Eigenschaftswerte in der Vorlage als Standardwerte für diesen Projekttyp betrachtet werden. In anderen Projekttypen weisen die Eigenschaften möglicherweise unterschiedliche Standardwerte auf.

Der Wert einer Projekteigenschaft wird in Fettdruck angezeigt, wenn er geändert wird. Eine Projekteigenschaft kann aus den folgenden Gründen geändert werden:

- Der Anwendungs-Assistent ändert die Eigenschaft, da ein anderer Eigenschaftswert als der in der Projektvorlage angegebene erforderlich ist.

- Sie können einen anderen Eigenschaftswert im Dialogfeld **Neues Projekt** angeben.

- Das Angeben eines anderen Eigenschaftswert erfolgt auf einer Projekteigenschaftsseite.

> [!TIP]
> Zeigen Sie die endgültigen Eigenschaftswerten an, die MSBuild zum Erstellen des Projekts verwendet, indem Sie die Präprozessorausgabedatei überprüfen, die Sie mithilfe der folgenden Befehlszeile erstellen können: **MSBuild /preprocess:** *preprocessor_output_filename*<sub>opt</sub> *project_filename*<sub>opt</sub>.

## <a name="resetting-properties"></a>Zurücksetzen der Eigenschaften

Wenn Sie das Dialogfeld **Eigenschaftenseiten** für ein Projekt anzeigen möchten und der Projektknoten im **Projektmappen-Explorer** ausgewählt ist, können Sie für viele Eigenschaften die Option **Vom übergeordneten Projekt erben oder Projektstandard** auswählen oder den Wert anderweitig ändern.

Wenn Sie das Dialogfeld **Eigenschaftenseiten** für ein Projekt anzeigen möchten und eine Datei im **Projektmappen-Explorer** ausgewählt ist, können Sie für viele Eigenschaften die Option **Vom übergeordneten Projekt erben oder Projektstandard** auswählen oder den Wert anderweitig ändern. Wenn das Projekt jedoch viele Dateien enthält, die Eigenschaftswerte aufweisen, welche sich von den Projektstandardwerten unterscheiden, nimmt das Erstellen des Projekts längere Zeit in Anspruch.

> [!TIP]
> Klicken Sie zum Aktualisieren des Dialogfelds **Eigenschaftenseiten** auf **Anwenden**, damit die neuesten Auswahlen angezeigt werden.

Bei den meisten Projektstandardwerten handelt es sich um Systemstandardwerte (Plattform). Einige Projektstandardwerte werden aus den Stylesheets abgeleitet, die angewendet werden, wenn Sie die Eigenschaften im Abschnitt **Projektstandards** der Konfigurationseigenschaftsseite **Allgemein** für das Projekt aktualisieren. Weitere Informationen finden Sie unter [General Property Page (Project) (Eigenschaftenseite „Allgemein“ (Projekt))](../ide/general-property-page-project.md).

## <a name="specifying-user-defined-values"></a>Angeben von benutzerdefinierten Werten

Sie müssen den Wert für bestimmte Eigenschaften definieren. Ein benutzerdefinierter Wert kann eine oder mehrere alphanumerische Zeichen oder Projektdatei-Makronamen enthalten. Einige dieser Eigenschaften können nur einen benutzerdefinierten Wert verwenden. Andere wiederum können eine durch Semikolons getrennte Liste von mehreren Werten verwenden.

Um einen benutzerdefinierten Wert für eine Eigenschaft anzugeben oder eine Liste, wenn die Eigenschaft mehrere benutzerdefinierte Werte übernimmt, müssen Sie in der Spalte rechts neben dem Eigenschaftsnamen eine der folgenden Aktionen ausführen:

- Geben Sie den Wert oder die Liste der Werte ein.

- Klicken Sie auf den Dropdownpfeil. Wenn **Bearbeiten** verfügbar ist, klicken Sie darauf, und geben Sie dann in das Textfeld den Wert oder die Liste der Werte ein. Eine alternative Möglichkeit zum Angeben einer Liste besteht darin, jeden Wert in einer getrennten Zeile im Textfeld einzugeben. Auf der Eigenschaftsseite werden die Werte als eine durch Semikolons getrennte Liste angezeigt.

   Klicken Sie zum Einfügen eines Projektdateimakros als Wert auf **Makros**, und doppelklicken Sie dann auf den Makronamen.

- Klicken Sie auf den Dropdownpfeil. Wenn **Durchsuchen** verfügbar ist, klicken Sie darauf, und wählen Sie dann mindestens einen Wert aus.

Bei einer mehrwertigen Eigenschaft steht die Option **Vom übergeordneten Projekt erben oder Projektstandard** zur Verfügung, wenn Sie auf den Dropdownpfeil in der Spalte rechts neben dem Eigenschaftsnamen klicken und anschließend auf **Bearbeiten** klicken. Die Option ist standardmäßig ausgewählt.

Beachten Sie, dass eine Eigenschaftsseite nur die Einstellungen auf der aktuellen Ebene für eine mehrwertige Eigenschaft anzeigt, die aus einer anderen Ebene geerbt werden. Wenn beispielsweise eine Datei im **Projektmappen-Explorer** ausgewählt ist und Sie die Eigenschaft für die **C/C++-Präprozessordefinitionen** auswählen, werden Definitionen auf Dateiebene angezeigt, geerbte Definitionen auf Projektebene jedoch nicht. Klicken Sie zum Anzeigen der Werte auf der aktuellen Ebene und der geerbten Werte auf den Dropdownpfeil in der Spalte rechts neben dem Eigenschaftsnamen, und klicken Sie dann auf **Bearbeiten**. Beim Verwenden des [Visual C++-Projektmodells](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine) gilt dieses Verhalten auch für die Objekte in Dateien und Projekten. Wenn Sie die Werte in einer Eigenschaft auf Dateiebene abfragen, erhalten Sie demnach nicht die Werte für dieselbe Eigenschaft auf der Projektebene. Sie müssen die Werte der Eigenschaft auf der Projektebene explizit abrufen. Zudem stammen einige geerbten Werte einer Eigenschaft möglicherweise von einem Stylesheet, auf das nicht programmgesteuert zugegriffen werden kann.

## <a name="in-this-section"></a>In diesem Abschnitt

[Erweitert, Manifesttool, Konfigurationseigenschaften, Dialogfeld „\<Projektname>-Eigenschaftenseiten“](../ide/advanced-manifest-tool.md)

[Eigenschaftenseiten "Befehlszeile"](../ide/command-line-property-pages.md)

[Eigenschaftenseite für benutzerdefinierten Buildschritt: Allgemein](../ide/custom-build-step-property-page-general.md)

[Adding references (Hinzufügen von Verweisen)](../ide/adding-references-in-visual-cpp-projects.md)

[Eigenschaftenseite "Allgemein" (Datei)](../ide/general-property-page-file.md)

[Eigenschaftenseite „Allgemein“ (Projekt)](../ide/general-property-page-project.md)

[Allgemein, Manifesttool, Konfigurationseigenschaften, Dialogfeld „\<Projektname>-Eigenschaftenseiten“](../ide/general-manifest-tool-configuration-properties.md)

[Eigenschaftenseiten "HLSL"](../ide/hlsl-property-pages.md)

[Eigenschaftenseiten "HLSL": Erweitert](../ide/hlsl-property-pages-advanced.md)

[Eigenschaftenseiten "HLSL": Allgemein](../ide/hlsl-property-pages-general.md)

[Eigenschaftenseiten "HLSL": Ausgabedateien](../ide/hlsl-property-pages-output-files.md)

[Eingabe und Ausgabe, Manifesttool, Konfigurationseigenschaften, Dialogfeld „\<Projektname>-Eigenschaftenseiten“](../ide/input-and-output-manifest-tool.md)

[Isolated COM, Manifesttool, Konfigurationseigenschaften, Dialogfeld „\<Projektname>-Eigenschaftenseiten“](../ide/isolated-com-manifest-tool.md)

[Eigenschaftenseiten "Linker"](../ide/linker-property-pages.md)

[Eigenschaftenseite "Verwaltete Ressourcen"](../ide/managed-resources-property-page.md)

[Manifesttool-Eigenschaftenseiten](../ide/manifest-tool-property-pages.md)

[Eigenschaftenseiten "MIDL"](../ide/midl-property-pages.md)

[Eigenschaftenseiten "MIDL": "Erweitert"](../ide/midl-property-pages-advanced.md)

[Eigenschaftenseiten "MIDL": "Allgemein"](../ide/midl-property-pages-general.md)

[Eigenschaftenseiten "MIDL": "Ausgabe"](../ide/midl-property-pages-output.md)

[Eigenschaftenseite "NMake"](../ide/nmake-property-page.md)

[Eigenschaftenseiten "Ressourcen"](../ide/resources-property-pages.md)

[Eigenschaftenseite "VC++-Verzeichnisse"](../ide/vcpp-directories-property-page.md)

[Eigenschaftenseite "Webverweise"](../ide/web-references-property-page.md)

[Eigenschaftenseite "Tool zum Generieren von XML-Daten"](../ide/xml-data-generator-tool-property-page.md)

[Eigenschaftenseiten für das Tool XML-Dokument-Generator](../ide/xml-document-generator-tool-property-pages.md)

## <a name="see-also"></a>Siehe auch

[Gewusst wie: Erstellen und Entfernen von Projektabhängigkeiten](/visualstudio/ide/how-to-create-and-remove-project-dependencies)  
[Gewusst wie: Erstellen und Bearbeiten von Konfigurationen](/visualstudio/ide/how-to-create-and-edit-configurations)  
