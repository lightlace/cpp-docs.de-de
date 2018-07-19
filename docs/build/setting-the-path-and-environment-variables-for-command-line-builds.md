---
title: Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds | Microsoft Docs
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
ms.openlocfilehash: 0b72f13fe25330b81a48d1447b707bdc4626ab3f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381134"
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds

Visual C++-Befehlszeilen-Buildtools erfordern mehrere Umgebungsvariablen, die angepasst werden, für die Installation und Build-Konfiguration. Nach der Installation einer C++-arbeitsauslastung durch den [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Installer erstellt angepasste Befehlsdateien oder Batchdateien, die die erforderlichen Umgebungsvariablen festlegen. Das Installationsprogramm verwendet dann diese Befehlsdateien zum Erstellen von Verknüpfungen für die Windows-Startmenü zu einer Developer-Eingabeaufforderungsfenster zu öffnen. Die folgenden Tastenkombinationen, richten Sie die Umgebungsvariablen für eine bestimmte Buildkonfiguration. Wenn Sie die Befehlszeilentools verwenden möchten, können Sie eine dieser Verknüpfungen ausführen oder Sie können ein einfaches Eingabeaufforderungsfenster öffnen, und führen Sie einen benutzerdefinierten Befehl Dateien in der Buildumgebung für die Konfiguration selbst festlegen. Weitere Informationen finden Sie unter [C/C++-Code erstellen, in der Befehlszeile](building-on-the-command-line.md).  
  
Die Visual C++-Befehlszeilentools verwenden die Umgebungsvariablen PATH, TMP, INCLUDE, LIB und LIBPATH und auch andere Umgebungsvariablen, die spezifisch für Ihre installierten Tools, Plattformen und SDKs verwenden. Auch eine einfache [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Installation kann 20 oder mehr Umgebungsvariablen festgelegt. Da die Werte dieser Umgebungsvariablen spezifisch für die Installation und die Auswahl der Buildkonfiguration sind und durch produktaktualisierungen oder -Upgrades geändert werden können, es wird dringend empfohlen, dass Sie eine Developer-eingabeaufforderungsverknüpfung oder eines verwenden die Benutzerdefinierte Befehlsdateien, die sie festlegen, statt sie in der Windows-Umgebung selbst festzulegen. 

Um festzustellen, welche Umgebungsvariablen durch eine Developer-eingabeaufforderungsverknüpfung festgelegt sind, können Sie den SET-Befehl. Ein einfaches Eingabeaufforderungsfenster öffnen und die Ausgabe des Befehls "SET" für eine Basislinie zu erfassen. Öffnen Sie ein Developer-Eingabeaufforderungsfenster, und erfassen Sie die Ausgabe des Befehls "SET" für den Vergleich zu. Einem Vergleichstool wie in der Visual Studio-IDE integriert kann hilfreich sein, vergleichen die Umgebungsvariablen und sehen, was von der Developer-Eingabeaufforderung festgelegt ist. Informationen, die bestimmte Umgebungsvariablen, die durch den Compiler und Linker verwendet, finden Sie unter [CL-Umgebungsvariablen](../build/reference/cl-environment-variables.md) und [LINK-Umgebungsvariablen](../build/reference/link-environment-variables.md).  
  
> [!NOTE]
>  Mehrere Befehlszeilentools oder Tooloptionen möglicherweise Administratorrechte erforderlich. Wenn Sie Berechtigungsproblemen verfügen, wenn Sie sie verwenden, es wird empfohlen, dass Sie die Developer-Eingabeaufforderungsfenster öffnen, indem Sie die **als Administrator ausführen** Option. Unter Windows 10 mit der rechten Maustaste um das Kontextmenü für das Eingabeaufforderungsfenster zu öffnen, und wählen Sie dann **weitere**, **als Administrator ausführen**.  
  
## <a name="see-also"></a>Siehe auch  

[Erstellen von C/C++-Code in der Befehlszeile](../build/building-on-the-command-line.md)   
[Verknüpfen](../build/reference/linking.md)   
[Optionen des Linkers](../build/reference/linker-options.md)   
[Kompilieren eines C/C++-Programms](../build/reference/compiling-a-c-cpp-program.md)   
[Compileroptionen](../build/reference/compiler-options.md)