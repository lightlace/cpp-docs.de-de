---
title: Eigenschaftenseiten (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b0c342148266dff9551d2705f8095250daf2b096
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="property-pages-visual-c"></a>Eigenschaftenseiten (Visual C++)

Mithilfe von Eigenschaftenseiten können Sie Einstellungen für Visual Studio-Projekte angeben. So öffnen die **Eigenschaftenseiten** Dialogfeld für ein Visual Studio-Projekt im die **Projekt** im Menü Wählen Sie **Eigenschaften**.

Sie können Projekteinstellungen angeben, damit sie alle Buildkonfigurationen übernehmen. Alternativ können Sie unterschiedliche Projekteigenschaften für jede Buildkonfiguration angeben. Beispielsweise können Sie bestimmte Einstellungen für die Releasekonfiguration und andere Einstellungen für die Debugkonfiguration festlegen.

Nicht alle verfügbare Seiten werden unbedingt angezeigt, der **Eigenschaftenseiten** (Dialogfeld). Welche Seiten angezeigt werden, hängt von den Dateitypen im Projekt ab.

Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).

Nicht-Windows-Projekte finden Sie unter [Linux C++-Eigenschaft des Seitenverweises](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->.

## <a name="default-properties-vs-modified-properties"></a>Standardeigenschaften im Vergleich mit geänderten Eigenschaften

Bei Verwendung der **neues Projekt** mithilfe der angegebenen Projektvorlage im Dialogfeld zum Erstellen eines Projekts, Visual Studio um die Projekteigenschaften zu initialisieren. Daher können die Eigenschaftswerte in der Vorlage als Standardwerte für diesen Projekttyp betrachtet werden. In anderen Projekttypen weisen die Eigenschaften möglicherweise unterschiedliche Standardwerte auf.

Der Wert einer Projekteigenschaft wird in Fettdruck angezeigt, wenn er geändert wird. Eine Projekteigenschaft kann aus den folgenden Gründen geändert werden:

- Der Anwendungs-Assistent ändert die Eigenschaft, da ein anderer Eigenschaftswert als der in der Projektvorlage angegebene erforderlich ist.

- Geben Sie einen anderen Eigenschaftswert in der **neues Projekt** (Dialogfeld).

- Das Angeben eines anderen Eigenschaftswert erfolgt auf einer Projekteigenschaftsseite.

> [!TIP]
> Um die endgültige Satz von Eigenschaftenwerten anzuzeigen, die MSBuild verwendet, um das Projekt zu erstellen, überprüfen Sie die Präprozessorausgabedatei, die mit dieser Befehlszeile erstellt werden kann: **MSBuild / vorverarbeiten:** *Preprocessor_output_ FileName*<sub>opt</sub> *Project_filename*<sub>abonnieren</sub>

## <a name="resetting-properties"></a>Zurücksetzen der Eigenschaften

Beim Anzeigen der **Eigenschaftenseiten** für ein Projekt und den Projektknoten im Dialogfeld ausgewählt ist **Projektmappen-Explorer**, für viele Eigenschaften können Sie auswählen **erben von der übergeordneten oder ein Projekt Standardwerte** oder ändern Sie den Wert anderweitig.

Beim Anzeigen der **Eigenschaftenseiten** für ein Projekt und eine Datei im Dialogfeld ausgewählt ist **Projektmappen-Explorer**, für viele Eigenschaften können Sie auswählen **erben von der übergeordneten oder ein Projekt standardmäßig** oder ändern Sie den Wert anderweitig. Wenn das Projekt jedoch viele Dateien enthält, die Eigenschaftswerte aufweisen, welche sich von den Projektstandardwerten unterscheiden, nimmt das Erstellen des Projekts längere Zeit in Anspruch.

> [!TIP]
> Aktualisieren der **Eigenschaftenseiten** wählen Sie im Dialogfeld so, dass er die neuesten Auswahlen anzeigt **übernehmen**.

Bei den meisten Projektstandardwerten handelt es sich um Systemstandardwerte (Plattform). Einige Projektstandardwerte leiten sich aus den Stylesheets, die angewendet werden, beim Aktualisieren der Eigenschaften in der **Projektstandardwerte** Teil der **allgemeine** konfigurationseigenschaftsseite für das Projekt. Weitere Informationen finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../ide/general-property-page-project.md).

## <a name="specifying-user-defined-values"></a>Angeben von benutzerdefinierten Werten

Sie müssen den Wert für bestimmte Eigenschaften definieren. Ein benutzerdefinierter Wert kann eine oder mehrere alphanumerische Zeichen oder Projektdatei-Makronamen enthalten. Einige dieser Eigenschaften können nur einen benutzerdefinierten Wert verwenden. Andere wiederum können eine durch Semikolons getrennte Liste von mehreren Werten verwenden.

Um einen benutzerdefinierten Wert für eine Eigenschaft anzugeben oder eine Liste, wenn die Eigenschaft mehrere benutzerdefinierte Werte übernimmt, müssen Sie in der Spalte rechts neben dem Eigenschaftsnamen eine der folgenden Aktionen ausführen:

- Geben Sie den Wert oder die Liste der Werte ein.

- Wählen Sie den Dropdown Pfeil. Wenn **bearbeiten** verfügbar ist, wählen Sie sie aus, und geben Sie dann in das Textfeld den Wert oder eine Liste von Werten. Eine alternative Möglichkeit zum Angeben einer Liste besteht darin, jeden Wert in einer getrennten Zeile im Textfeld einzugeben. Auf der Eigenschaftsseite werden die Werte als eine durch Semikolons getrennte Liste angezeigt.

   Um eine Projektdateimakros als Wert einzufügen, wählen Sie **Makros** und doppelklicken Sie dann auf den Makronamen.

- Wählen Sie den Dropdown Pfeil. Wenn **Durchsuchen** verfügbar ist, wählen Sie sie aus, und wählen Sie dann einen oder mehrere Werte.

Bei einer mehrwertigen Eigenschaft der **erben von der übergeordneten oder ein Projekt standardmäßig** Option ist verfügbar, wenn Sie den Dropdown Pfeil in der Spalte rechts neben dem Eigenschaftsnamen auswählen, und Sie dann wählen **bearbeiten**. Die Option ist standardmäßig ausgewählt.

Beachten Sie, dass eine Eigenschaftsseite nur die Einstellungen auf der aktuellen Ebene für eine mehrwertige Eigenschaft anzeigt, die aus einer anderen Ebene geerbt werden. Angenommen, eine Datei ausgewählt ist **Projektmappen-Explorer** , und wählen Sie die C/C++- **Präprozessordefinitionen** -Eigenschaft, Definitionen auf Dateiebene angezeigt, aber geerbte Definitionen auf Projektebene werden nicht angezeigt. Anzeigen der aktuellen Ebene und geerbte Werte, wählen den Dropdown Pfeil in der Spalte rechts neben dem Eigenschaftsnamen, und wählen Sie dann **bearbeiten**. Bei Verwendung der [Visual C++-Projektmodells](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine), dieses Verhalten ist ebenfalls gültig für die Objekte in Dateien und Projekten. Wenn Sie die Werte in einer Eigenschaft auf Dateiebene abfragen, erhalten Sie demnach nicht die Werte für dieselbe Eigenschaft auf der Projektebene. Sie müssen die Werte der Eigenschaft auf der Projektebene explizit abrufen. Zudem stammen einige geerbten Werte einer Eigenschaft möglicherweise von einem Stylesheet, auf das nicht programmgesteuert zugegriffen werden kann.

## <a name="in-this-section"></a>In diesem Abschnitt

[Erweitert, Manifesttool, Konfigurationseigenschaften, \<Projektname > Eigenschaftenseiten (Dialogfeld)](../ide/advanced-manifest-tool.md)

[Eigenschaftenseiten "Befehlszeile"](../ide/command-line-property-pages.md)

[Eigenschaftenseite für benutzerdefinierten Buildschritt: Allgemein](../ide/custom-build-step-property-page-general.md)

[Hinzufügen von verweisen](../ide/adding-references-in-visual-cpp-projects.md)

[Eigenschaftenseite "Allgemein" (Datei)](../ide/general-property-page-file.md)

[Eigenschaftenseite „Allgemein“ (Projekt)](../ide/general-property-page-project.md)

[Tool Allgemein, Manifesttool, Konfigurationseigenschaften, \<Projektname > Eigenschaftenseiten (Dialogfeld)](../ide/general-manifest-tool-configuration-properties.md)

[Eigenschaftenseiten "HLSL"](../ide/hlsl-property-pages.md)

[Eigenschaftenseiten "HLSL": Erweitert](../ide/hlsl-property-pages-advanced.md)

[Eigenschaftenseiten "HLSL": Allgemein](../ide/hlsl-property-pages-general.md)

[Eigenschaftenseiten "HLSL": Ausgabedateien](../ide/hlsl-property-pages-output-files.md)

[Eingabe und Ausgabe, Tools, Konfigurationseigenschaften, Manifest \<Projektname > Eigenschaftenseiten (Dialogfeld)](../ide/input-and-output-manifest-tool.md)

[Isolierte COM, Manifesttool, Konfigurationseigenschaften, \<Projektname > Eigenschaftenseiten (Dialogfeld)](../ide/isolated-com-manifest-tool.md)

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
