---
title: Festlegen der Pfad-und Umgebungsvariablen für Befehlszeilenbuilds
ms.custom: conceptual
ms.date: 07/24/2019
helpviewer_keywords:
- environment variables [C++]
- VCVARS32.bat file
- cl.exe compiler [C++], environment variables
- LINK tool [C++], environment variables
- PATH reserved word
- INCLUDE reserved word
- LINK tool [C++], path
- LIB environment variable
- compiling source code [C++], from command line
- environment variables [C++], CL compiler
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
ms.openlocfilehash: 6e7882b169805e3c62596341986a83d476ac5ec1
ms.sourcegitcommit: ce3393846c86e7905ff0c86e4cd6610476809585
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2019
ms.locfileid: "68492150"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>Festlegen der Pfad-und Umgebungsvariablen für Befehlszeilenbuilds

Die Befehls C++ Zeilen-Buildtools von Microsoft (MSVC) erfordern mehrere Umgebungsvariablen, die für die Installations-und Buildkonfiguration angepasst sind. Wenn eine C++ Arbeitsauslastung vom Visual Studio-Installer installiert wird, werden angepasste Befehls Dateien oder Batch Dateien erstellt, die die erforderlichen Umgebungsvariablen festlegen. Das Installationsprogramm verwendet diese Befehls Dateien dann, um Verknüpfungen für das Windows-Startmenü zu erstellen, um ein Entwickler-Eingabe Aufforderungs Fenster zu öffnen. Diese Tastenkombinationen richten die Umgebungsvariablen für eine bestimmte Buildkonfiguration ein. Wenn Sie die Befehlszeilen Tools verwenden möchten, können Sie eine dieser Tastenkombinationen ausführen, oder Sie können ein einfaches Eingabe Aufforderungs Fenster öffnen und dann eine der benutzerdefinierten Befehls Dateien ausführen, um die buildkonfigurationsumgebung selbst festzulegen. Weitere Informationen finden Sie unter [Verwenden des MSVC-Toolsets von der Befehlszeile aus](building-on-the-command-line.md). Informationen zum Verwenden der Befehls Dateien mit einer einfachen Eingabeaufforderung finden Sie im Abschnitt zu den Speicher [Orten der Developer-Befehlsdatei](building-on-the-command-line.md#developer_command_file_locations).

Die MSVC-Befehlszeilen Tools verwenden die Umgebungsvariablen "Path", "tmp", "include", "lib" und "LIBPATH" und verwenden auch andere Umgebungsvariablen, die für die installierten Tools, Plattformen und sdker spezifisch sind. Selbst bei einer einfachen Visual Studio-Installation werden möglicherweise 20 oder mehr Umgebungsvariablen festgelegt. Da die Werte dieser Umgebungsvariablen spezifisch für Ihre Installation und die gewünschte Buildkonfiguration sind und durch Produktupdates oder-Upgrades geändert werden können, wird dringend empfohlen, dass Sie eine Eingabe Aufforderungs Verknüpfung für Entwickler oder eine der folgenden Befehle verwenden: zum Festlegen angepasster Befehls Dateien, anstatt Sie selbst in der Windows-Umgebung festzulegen.

Zum Anzeigen der Umgebungsvariablen, die von einer Eingabeaufforderung für Entwickler-Eingabeaufforderung festgelegt werden, können Sie den SET-Befehl verwenden. Öffnen Sie ein einfaches Eingabe Aufforderungs Fenster, und erfassen Sie die Ausgabe des SET-Befehls für eine Baseline. Öffnen Sie ein Developer-Eingabe Aufforderungs Fenster, und erfassen Sie die Ausgabe des SET-Befehls für den Vergleich. Ein Diff-Tool wie das, das in die Visual Studio-IDE integriert ist, kann nützlich sein, um die Umgebungsvariablen zu vergleichen und anzuzeigen, was von der Developer-Eingabeaufforderung festgelegt wird. Informationen zu den spezifischen Umgebungsvariablen, die vom Compiler und Linker verwendet werden, finden Sie unter [CL-Umgebungsvariablen](reference/cl-environment-variables.md).

> [!NOTE]
>  Für mehrere Befehlszeilen Tools oder Tool Optionen sind möglicherweise Administrator Berechtigungen erforderlich. Wenn bei der Verwendung von Berechtigungs Problemen auftreten, empfiehlt es sich, das Eingabe Aufforderungs Fenster für Entwickler mit der Option **als Administrator ausführen zu** öffnen. Klicken Sie unter Windows 10 mit der rechten Maustaste, um das Kontextmenü für das Eingabe Aufforderungs Fenster zu öffnen, und wählen Sie dann **mehr**, **als Administrator ausführen**aus.

## <a name="see-also"></a>Siehe auch

[Verwenden des MSVC-Toolsets über die Befehlszeile](building-on-the-command-line.md)<br/>
[MSVC-Linkerreferenz](reference/linking.md)<br/>
[MSVC-Linkeroptionen](reference/linker-options.md)<br/>
[MSVC-Compilerreferenz](reference/compiling-a-c-cpp-program.md)<br/>
[MSVC-Compileroptionen](reference/compiler-options.md)
