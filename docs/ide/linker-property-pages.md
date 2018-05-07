---
title: Linker-Eigenschaftenseiten | Microsoft Docs
ms.custom: ''
ms.date: 11/21/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
dev_langs:
- C++
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cec232bb4e4f2f6ac1ab9af703b368eec0ba5dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-property-pages"></a>Linker-Eigenschaftenseiten

Dieses Thema enthält die folgenden Eigenschaften der **allgemeine** Linker-Eigenschaftenseite. Die Linux-Version auf dieser Seite finden Sie unter [Linker-Eigenschaften (Linux C++)](../linux/prop-pages/linker-linux.md).

## <a name="general-page-properties"></a>Seite "Allgemein"-Eigenschaften

### <a name="ignore-import-library"></a>Importbibliothek ignorieren

Diese Eigenschaft weist den Linker nicht, um alle von dieser Build einem abhängigen Projekt erstellte LIB-Ausgabe zu verknüpfen. Auf diese Weise kann das Projektsystem DLL-Dateien verarbeiten, durch die während der Erstellung keine LIB-Datei generiert wird. Wenn ein Projekt von einem anderen Projekt abhängig, der eine DLL generiert ist, verknüpft das Projektsystem automatisch die LIB-Datei, die von diesem untergeordneten Projekt erstellt. Diese Verknüpfung ist für Projekte, die COM-DLLs oder reine Ressourcen-DLLs erstellen, u. U. nicht erforderlich. Diese DLLs exportieren keine wichtigen Daten. Wenn eine DLL über keine Exportdaten verfügt, löst der Linker keine LIB-Datei. Wenn keine LIB-Exportdatei auf dem Datenträger vorhanden ist, und das Projektsystem den Linker weist an dieser (fehlenden) DLL verknüpfen, schlägt fehl, der Link. Verwenden der **Importbibliothek ignorieren** Eigenschaft, um dieses Problem zu beheben. Bei Festlegung auf **Ja**, das Projektsystem das Vorhandensein oder fehlen der LIB-Datei ignoriert und bewirkt, dass jedes Projekt, das von diesem Projekt nicht mit der vorhandenen LIB-Datei verknüpfen abhängig ist.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>.

### <a name="register-output"></a>Ausgabe registrieren

Führt `regsvr32.exe /s $(TargetPath)` auf die Buildausgabe, dies ist nur für DLL-Projekte zulässig. Bei EXE-Projekten wird diese Eigenschaft ignoriert. Um eine .exe-Ausgabedatei registrieren möchten, legen Sie ein Postbuildereignis für die Konfiguration für die benutzerdefinierte Registrierung auszuführen, die immer erforderlich, damit registrierte .exe-Dateien ist ein.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>.

### <a name="per-user-redirection"></a>Umleitung pro Benutzer

Registrierung in Visual Studio hat herkömmlicherweise in HKEY_CLASSES_ROOT (HKCR) ausgeführt wurde. Um auf HKCR zuzugreifen, müssen Sie Visual Studio im erweiterten Modus mit Windows Vista und höheren Betriebssystemen ausführen. Entwickler möchten die Software nicht immer im erhöhten Modus ausführen, müssen aber trotzdem mit der Registrierung arbeiten. Die Umleitung pro Benutzer ermöglicht Ihnen die Registrierung, ohne die Software in diesem Modus ausführen zu müssen.

Umleitung pro Benutzer erzwingt keine Schreibvorgänge für HKCR geschriebenen Daten zu öffnende HKEY umgeleitet werden\_aktuelle\_Benutzer (HKCU). Wenn die Umleitung pro Benutzer deaktiviert ist, kann dies [Projekt erstellen Fehler PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) Wenn das Programm versucht, in HKCR zu schreiben.

### <a name="link-library-dependencies"></a>Bibliothekabhängigkeiten verknüpfen

Gibt an, ob die LIB-Dateien zu verknüpfen, die durch abhängige Projekte erstellt werden. In der Regel wird ein Link in der LIB-Dateien hergestellt werden soll, aber dies möglicherweise nicht der Fall für bestimmte DLLs.

Sie können auch eine OBJ-Datei angeben, indem Sie den Dateinamen und den relativen Pfad, z. B. bereitstellen ".. \\.. \MyLibProject\MyObjFile.obj". Wenn der Quellcode für die OBJ-Datei #includes einen vorkompilierten Header, beispielsweise "PCH.h", und klicken Sie dann die pch.obj-Datei sich im gleichen Ordner wie MyObjFile.obj befindet, und Sie müssen außerdem pch.obj als zusätzliche Abhängigkeit hinzufügen.

### <a name="use-library-dependency-inputs"></a>Bibliothekabhängigkeitseingaben verwenden

Wenn durch ein abhängiges Projekt in einem umfangreichen Projekt eine LIB-Datei generiert wird, werden inkrementelle Verknüpfungen deaktiviert. Wenn es viele abhängige Projekte gibt, durch die LIB-Dateien generiert werden, kann die Anwendungserstellung längere Zeit in Anspruch nehmen. Wenn diese Eigenschaft festgelegt wird, um **Ja**, das Projektsystem in der OBJ-Dateien für LIB-erstellt von abhängigen Projekten, sodass inkrementelle Verknüpfungen.

Informationen über den Zugriff auf die **allgemeine** Linker-Eigenschaftenseite, finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).

## <a name="see-also"></a>Siehe auch

[VC++-Projekteinstellungen, Projekte und Projektmappen, Dialogfeld „Optionen“](/visualstudio/ide/reference/vcpp-project-settings-projects-and-solutions-options-dialog-box)  
[Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)  