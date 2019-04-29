---
title: Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds
ms.custom: conceptual
ms.date: 11/04/2016
f1_keywords:
- include
- Lib
- Path
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
ms.openlocfilehash: fed3360294bec724af09b87e5abd7c6bb22fa285
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315390"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds

Die Visual C++-Befehlszeilen-Buildtools erfordern mehrere Umgebungsvariablen, die angepasst werden, für die Installation und Build-Konfiguration. Bei eine C++-Workload von Visual Studio-Installer installiert ist, erstellt benutzerdefinierte Befehlsdateien oder Batchdateien, die die erforderlichen Umgebungsvariablen festlegen. Das Installationsprogramm verwendet dann diese Befehlsdateien zum Erstellen von Verknüpfungen für das Windows-Startmenü zu einem Developer-Eingabeaufforderungsfenster zu öffnen. Diese Tastenkombinationen, richten Sie die Umgebungsvariablen für eine bestimmte erstellen Konfiguration. Wenn Sie die Befehlszeilentools verwenden möchten, können Sie eine dieser Verknüpfungen ausführen oder Sie können ein einfaches Eingabeaufforderungsfenster öffnen, und führen Sie dann einen benutzerdefinierten Befehl Dateien in der Buildumgebung für die Konfiguration selbst festlegen. Weitere Informationen finden Sie unter [verwenden Sie das MSVC-Toolset, über die Befehlszeile](building-on-the-command-line.md).

Die Visual C++-Befehlszeilentools verwenden Sie die Umgebungsvariablen PATH, TMP, INCLUDE, LIB und LIBPATH und auch andere Umgebungsvariablen, die spezifisch für Ihre installierte Tools, Plattformen und -SDKs verwenden. Eine einfache Visual Studio-Installation kann 20 oder mehr Umgebungsvariablen festgelegt werden. Da die Werte dieser Variablen spezifisch für die Installation und die Auswahl der Buildkonfiguration sind und durch produktaktualisierungen oder -Upgrades geändert werden können, es wird dringend empfohlen, dass Sie eine Developer-eingabeaufforderungsverknüpfung oder eines verwenden die Benutzerdefinierte Befehlsdateien aus, die sie festlegen, statt sie in der Windows-Umgebung selbst festzulegen.

Um anzuzeigen, welche Umgebungsvariablen festgelegt werden, indem Sie eine Developer-eingabeaufforderungsverknüpfung, können Sie den SET-Befehl. Ein einfaches Eingabeaufforderungsfenster öffnen und die Ausgabe des Befehls "SET" für eine Baseline erfassen. Öffnen Sie ein Developer-Eingabeaufforderungsfenster, und erfassen Sie die Ausgabe des Befehls "SET" für den Vergleich. Ein difftool, z. B. die in Visual Studio-IDE integriert kann hilfreich sein, vergleichen die Umgebungsvariablen, und sehen, was von der Developer-Eingabeaufforderung festgelegt ist. Weitere Informationen, die bestimmte Umgebungsvariablen, die durch den Compiler und Linker verwendet, finden Sie unter [CL-Umgebungsvariablen](reference/cl-environment-variables.md).

> [!NOTE]
>  Mehrere Befehlszeilentools oder Tooloptionen möglicherweise Administratorberechtigungen erforderlich. Wenn Sie die Berechtigungsprobleme verfügen, wenn Sie diese verwenden, es wird empfohlen, Sie die Developer-Eingabeaufforderungsfenster mithilfe Öffnen der **als Administrator ausführen** Option. Unter Windows 10, mit der rechten Maustaste um das Kontextmenü für das Eingabeaufforderungsfenster zu öffnen, und wählen Sie dann **weitere**, **als Administrator ausführen**.

## <a name="see-also"></a>Siehe auch

[Verwenden des MSVC-Toolsets über die Befehlszeile](building-on-the-command-line.md)<br/>
[MSVC-Linkerreferenz](reference/linking.md)<br/>
[MSVC-Linkeroptionen](reference/linker-options.md)<br/>
[MSVC-Compilerreferenz](reference/compiling-a-c-cpp-program.md)<br/>
[MSVC-Compileroptionen](reference/compiler-options.md)
