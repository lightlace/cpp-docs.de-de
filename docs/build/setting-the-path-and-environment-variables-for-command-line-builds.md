---
title: Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds | Microsoft-Dokumentation
ms.custom: conceptual
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- include
- Lib
- Path
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e4b24e3ec209273b0f547c99685e8e804a74bc0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724247"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds

Die Visual C++-Befehlszeilen-Buildtools erfordern mehrere Umgebungsvariablen, die angepasst werden, für die Installation und Build-Konfiguration. Bei eine C++-Workload von Visual Studio-Installer installiert ist, erstellt benutzerdefinierte Befehlsdateien oder Batchdateien, die die erforderlichen Umgebungsvariablen festlegen. Das Installationsprogramm verwendet dann diese Befehlsdateien zum Erstellen von Verknüpfungen für das Windows-Startmenü zu einem Developer-Eingabeaufforderungsfenster zu öffnen. Diese Tastenkombinationen, richten Sie die Umgebungsvariablen für eine bestimmte erstellen Konfiguration. Wenn Sie die Befehlszeilentools verwenden möchten, können Sie eine dieser Verknüpfungen ausführen oder Sie können ein einfaches Eingabeaufforderungsfenster öffnen, und führen Sie dann einen benutzerdefinierten Befehl Dateien in der Buildumgebung für die Konfiguration selbst festlegen. Weitere Informationen finden Sie unter [C/C++-Code erstellen, in der Befehlszeile](building-on-the-command-line.md).

Die Visual C++-Befehlszeilentools verwenden Sie die Umgebungsvariablen PATH, TMP, INCLUDE, LIB und LIBPATH und auch andere Umgebungsvariablen, die spezifisch für Ihre installierte Tools, Plattformen und -SDKs verwenden. Eine einfache Visual Studio-Installation kann 20 oder mehr Umgebungsvariablen festgelegt werden. Da die Werte dieser Variablen spezifisch für die Installation und die Auswahl der Buildkonfiguration sind und durch produktaktualisierungen oder -Upgrades geändert werden können, es wird dringend empfohlen, dass Sie eine Developer-eingabeaufforderungsverknüpfung oder eines verwenden die Benutzerdefinierte Befehlsdateien aus, die sie festlegen, statt sie in der Windows-Umgebung selbst festzulegen.

Um anzuzeigen, welche Umgebungsvariablen festgelegt werden, indem Sie eine Developer-eingabeaufforderungsverknüpfung, können Sie den SET-Befehl. Ein einfaches Eingabeaufforderungsfenster öffnen und die Ausgabe des Befehls "SET" für eine Baseline erfassen. Öffnen Sie ein Developer-Eingabeaufforderungsfenster, und erfassen Sie die Ausgabe des Befehls "SET" für den Vergleich. Ein difftool, z. B. die in Visual Studio-IDE integriert kann hilfreich sein, vergleichen die Umgebungsvariablen, und sehen, was von der Developer-Eingabeaufforderung festgelegt ist. Weitere Informationen, die bestimmte Umgebungsvariablen, die durch den Compiler und Linker verwendet, finden Sie unter [CL-Umgebungsvariablen](../build/reference/cl-environment-variables.md) und [LINK-Umgebungsvariablen](../build/reference/link-environment-variables.md).

> [!NOTE]
>  Mehrere Befehlszeilentools oder Tooloptionen möglicherweise Administratorberechtigungen erforderlich. Wenn Sie die Berechtigungsprobleme verfügen, wenn Sie diese verwenden, es wird empfohlen, Sie die Developer-Eingabeaufforderungsfenster mithilfe Öffnen der **als Administrator ausführen** Option. Unter Windows 10, mit der rechten Maustaste um das Kontextmenü für das Eingabeaufforderungsfenster zu öffnen, und wählen Sie dann **weitere**, **als Administrator ausführen**.

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-Code in der Befehlszeile](../build/building-on-the-command-line.md)<br/>
[Verknüpfen](../build/reference/linking.md)<br/>
[Linkeroptionen](../build/reference/linker-options.md)<br/>
[Kompilieren eines C/C++-Programms](../build/reference/compiling-a-c-cpp-program.md)<br/>
[Compileroptionen](../build/reference/compiler-options.md)