---
title: Linker-Eigenschaftenseiten
ms.date: 11/21/2017
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
ms.openlocfilehash: 1412531ae0ca9c0f5270df6df7b79ddc9be425ad
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825522"
---
# <a name="linker-property-pages"></a>Linker-Eigenschaftenseiten

In diesem Artikel werden die folgenden Eigenschaften erörtert, die sich auf der Linkereigenschaftenseite **Allgemein** befinden. Die Linux-Version dieser Seite finden Sie unter [Linkereigenschaften (Linux C++)](../../linux/prop-pages/linker-linux.md).

## <a name="general-page-properties"></a>Eigenschaftenseite „Allgemein“

### <a name="ignore-import-library"></a>Importbibliothek ignorieren

Durch diese Eigenschaft wird der Linker angewiesen, keine während des aktuellen Builds erstellte LIB-Ausgabe mit einem abhängigen Projekt zu verknüpfen. Auf diese Weise kann das Projektsystem DLL-Dateien verarbeiten, durch die während der Erstellung keine LIB-Datei generiert wird. Wenn ein Projekt von einem anderen Projekt abhängt, das eine DLL generiert, verknüpft das Projektsystem automatisch die LIB-Datei, die von diesem untergeordneten Projekt erstellt wurde. Diese Verknüpfung ist für Projekte, die COM-DLLs oder reine Ressourcen-DLLs erstellen, u. U. nicht erforderlich. Diese DLLs exportieren keine wichtigen Daten. Wenn eine DLL über keine Exportdaten verfügt, wird vom Linker auch keine LIB-Datei erstellt. Wenn auf dem Datenträger keine LIB-Exportdatei vorhanden ist und der Linker vom Projektsystem angewiesen wird, eine Verknüpfung mit dieser (fehlenden) DLL zu erstellen, schlägt die Verknüpfung fehl. Verwenden Sie die Eigenschaft **Importbibliothek ignorieren**, um dieses Problem zu beheben. Wenn Sie **Ja** auswählen, ignoriert das Projektsystem das Vorhandensein bzw. das Fehlen der LIB-Datei, und jedes von diesem Projekt abhängige Projekt wird daran gehindert, eine Verknüpfung mit der nicht vorhandenen LIB-Datei zu erstellen.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>.

### <a name="register-output"></a>Ausgabe registrieren

Führt `regsvr32.exe /s $(TargetPath)` für die Buildausgabe aus, dies ist nur für DLL-Projekte gültig. Bei EXE-Projekten wird diese Eigenschaft ignoriert. Legen Sie zum Registrieren einer EXE-Ausgabe für die Konfiguration ein Postbuildereignis fest, um die benutzerdefinierte Registrierung auszuführen, die für registrierte EXE-Dateien stets erforderlich ist.

Informationen zum programmgesteuerten Zugriff auf diese Eigenschaft finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>.

### <a name="per-user-redirection"></a>Umleitung pro Benutzer

Die Registrierung in Visual Studio erfolgte herkömmlicherweise in HKEY_CLASSES_ROOT (HKCR). Unter Windows Vista und höheren Betriebssystemen müssen Sie Visual Studio im erweiterten Modus ausführen, um auf HKCR zugreifen zu können. Entwickler möchten die Software nicht immer im erhöhten Modus ausführen, müssen aber trotzdem mit der Registrierung arbeiten. Die Umleitung pro Benutzer ermöglicht Ihnen die Registrierung, ohne die Software in diesem Modus ausführen zu müssen.

Die Umleitung pro Benutzer erzwingt eine Umleitung aller Schreibvorgänge für HKCR zu HKEY\_CURRENT\_USER (HKCU). Wenn die Umleitung pro Benutzer deaktiviert ist, kann der [Projektbuildfehler PRJ0050](../../error-messages/tool-errors/project-build-error-prj0050.md) auftreten, wenn das Programm versucht, in HKCR zu schreiben.

### <a name="link-library-dependencies"></a>Bibliothekabhängigkeiten verknüpfen

Gibt an, ob die LIB-Dateien verknüpft werden sollen, die von abhängigen Projekten erstellt wurden. In der Regel wird die Verknüpfung der LIB-Dateien empfohlen, jedoch ist dies für bestimmte DLLs nicht nötig.

Sie können auch eine OBJ-Datei angeben, indem Sie den Dateinamen und den relativen Pfad angeben, z.B. ..\\..\MyLibProject\MyObjFile.obj. Wenn der Quellcode für die OBJ-Datei einen vorkompilierten Header enthält (z.B. „pch.h“), befindet sich die „pch.obj“-Datei im gleichen Ordner wie „MyObjFile.obj“. Dann müssen Sie auch „pch.obj“ als zusätzliche Abhängigkeit hinzufügen.

### <a name="use-library-dependency-inputs"></a>Bibliothekabhängigkeitseingaben verwenden

Wenn durch ein abhängiges Projekt in einem umfangreichen Projekt eine LIB-Datei generiert wird, werden inkrementelle Verknüpfungen deaktiviert. Wenn es viele abhängige Projekte gibt, durch die LIB-Dateien generiert werden, kann die Anwendungserstellung längere Zeit in Anspruch nehmen. Wenn diese Eigenschaft auf **Ja** festgelegt ist, erstellt das Projektsystem in den OBJ-Dateien Verknüpfungen für LIB-Dateien, die von abhängigen Projekten generiert wurden, sodass inkrementelle Verknüpfungen möglich sind.

Informationen über den Zugriff auf die **allgemeine** Linker-Eigenschaftenseite, finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

## <a name="see-also"></a>Siehe auch

[VC++-Projekteinstellungen, Projekte und Projektmappen, Dialogfeld „Optionen“](/visualstudio/ide/reference/vcpp-project-settings-projects-and-solutions-options-dialog-box)<br>
[Referenz für C++-Projekt Seite](property-pages-visual-cpp.md)