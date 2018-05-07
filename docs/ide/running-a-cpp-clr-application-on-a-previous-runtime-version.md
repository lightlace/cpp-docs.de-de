---
title: Ausführen einer C++ - Clr-Anwendung auf einer früheren Laufzeitversion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [C++], runtime version specified
- versions [C++]
- app.config files, runtime version specified
- compatibility [C++], runtime version specified
- backward compatibility [C++], runtime version specified
- application deployment [C++], runtime version specified
- common language runtime [C++], version specified
- deploying applications [C++], runtime version specified
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f8e76930eb9191d27085d92a9d3a678812715fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Ausführen einer C++ /clr-Anwendung unter einer früheren Laufzeitversion
Sofern nicht anders angegeben, ist eine C++ .NET Framework-Anwendung erstellt, um auf die Version der common Language Runtime (CLR) ausgeführt werden, die der Compiler verwendet, um die Anwendung zu erstellen. Es ist jedoch möglich, dass eine .exe-Anwendung, die erstellt wird, für eine Version der Laufzeit auf anderen Versionen ausgeführt wird, die die erforderliche Funktionalität bereitstellt.  
  
 Um dies zu erreichen, geben Sie eine app.config-Datei, die Laufzeitversionsinformationen in enthält die `supportedRuntime` Tag.  
  
 Zur Laufzeit muss die Datei "App.config" einen Namen im Format aufweisen *FileName*config, wobei *FileName* ist der Name der ausführbaren Datei, die die Anwendung gestartet und es muss sich im gleichen Verzeichnis wie die ausführbare Datei. Wenn Ihre Anwendung TestApp.exe benannt wird, würde die Datei "App.config" z. B. TestApp.exe.config benannt werden.  
  
 Wenn Sie mehr als eine Laufzeitversion angeben und die Anwendung auf einem Computer mit mehr als einer installierten Laufzeitversion ausgeführt wird, verwendet die Anwendung die erste Version, die in der Datei "App.config" angegeben ist und installiert wird.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren Sie eine Anwendung, um eine .NET Framework-Version als Ziel](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717).  
  
 Für die Ausführung auf Version 1.0 oder Version 1.1 der CLR, eine Anwendung, die von der Visual C++ erstellt wird muss mithilfe von Compiler kompiliert werden [/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)