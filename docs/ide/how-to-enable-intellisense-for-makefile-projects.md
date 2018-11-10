---
title: 'Gewusst wie: Aktivieren von IntelliSense für Makefile-Projekte'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.IntelliSense
helpviewer_keywords:
- Makefile projects, IntelliSense
- IntelliSense, Makefile projects
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
ms.openlocfilehash: 80a4696856fea46c7749cfeb120535dcdab86282
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434670"
---
# <a name="how-to-enable-intellisense-for-makefile-projects"></a>Gewusst wie: Aktivieren von IntelliSense für Makefile-Projekte

IntelliSense wird in der IDE für Visual C++-Makefile-Projekte nicht ordnungsgemäß ausgeführt, wenn bestimmte Projekteinstellungen oder Compileroptionen nicht ordnungsgemäß eingerichtet sind. Verwenden Sie dieses Verfahren, um Visual C++-Makefile-Projekte zu konfigurieren, damit IntelliSense funktioniert, wenn Makefile-Projekte in der Visual Studio-Entwicklungsumgebung geöffnet sind.

### <a name="to-enable-intellisense-for-makefile-projects-in-the-ide"></a>So aktivieren Sie IntelliSense für Makefile-Projekte in der IDE

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten**. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Wählen Sie die Eigenschaftenseite **NMake** aus, und ändern Sie dann die Eigenschaften unter **IntelliSense** nach Bedarf.

   - Legen Sie die Eigenschaft **Präprozessordefinitionen** so fest, dass alle Präprozessorsymbole in Ihrem Makefile-Projekt definiert werden. Weitere Informationen finden Sie unter [/D (Preprocessor Definitions) (/D (Präprozessordefinitionen))](../build/reference/d-preprocessor-definitions.md).

   - Legen Sie die Eigenschaft **Includesuchpfad** so fest, dass die Liste von Verzeichnissen angegeben wird, in denen der Compiler sucht, um Dateiverweise aufzulösen, die an Präprozessordirektiven in Ihrem Makefile-Projekt übergeben werden. Weitere Informationen finden Sie unter [/I (Additional Include Directories) (/I (Zusätzliche Includeverzeichnisse))](../build/reference/i-additional-include-directories.md).

         For projects that are built using CL.EXE from a Command Window, set the **INCLUDE** environment variable to specify directories that the compiler will search to resolve file references that are passed to preprocessor directives in your makefile project.

   - Legen Sie die Eigenschaft **Erzwungene Includedateien** fest, um anzugeben, welche Headerdateien bei der Erstellung des Makefile-Projekts verarbeitet werden sollen. Weitere Informationen finden Sie unter [/FI (Name Forced Include File) (/FI (Name der expliziten Includedatei))](../build/reference/fi-name-forced-include-file.md).

   - Legen Sie die Eigenschaft **Assemblysuchpfad** fest, um die Liste von Verzeichnissen anzugeben, in denen der Compiler sucht, um Verweise auf .NET-Assemblys in Ihrem Projekt aufzulösen. Weitere Informationen finden Sie unter [/AI (Specify Metadata Directories) (/AI (Metadatenverzeichnisse festlegen))](../build/reference/ai-specify-metadata-directories.md).

   - Legen Sie die Eigenschaft **Erzwungene Verwendung von Assemblys** fest, um anzugeben, welche .NET-Assemblys bei der Erstellung des Makefile-Projekts verarbeitet werden sollen. Weitere Informationen finden Sie unter [/FU (Name Forced #using File) (/FU (Name der erzwungenen #using-Datei))](../build/reference/fu-name-forced-hash-using-file.md).

   - Legen Sie die Eigenschaft **Zusätzliche Optionen** fest, um zusätzliche Compileroptionen anzugeben, die von IntelliSense beim Analysieren von C++-Dateien verwendet werden.

1. Klicken Sie auf **OK**, um die Eigenschaftenseiten zu schließen.

1. Verwenden Sie den Befehl **Alle speichern**, um die geänderten Projekteinstellungen zu speichern.

Führen Sie das nächste Mal, wenn Sie Ihr Makefile-Projekt in der Visual Studio-Entwicklungsumgebung öffnen, den Befehl **Projektmappe bereinigen** und anschließend **Projektmappe erstellen** im Makefile-Projekt aus. IntelliSense sollte nun ordnungsgemäß in der IDE funktionieren.

## <a name="see-also"></a>Siehe auch

[Verwenden von IntelliSense](/visualstudio/ide/using-intellisense)<br>
[NMAKE-Referenz](../build/nmake-reference.md)<br>
[Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)