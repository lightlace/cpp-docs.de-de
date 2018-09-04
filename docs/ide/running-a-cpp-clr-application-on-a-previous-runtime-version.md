---
title: Ausführen einer C++/CLR-Anwendung unter einer früheren Runtimeversion | Microsoft-Dokumentation
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
ms.openlocfilehash: 20a20002397e285680927fe519e4eac7b68cc343
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216561"
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Ausführen einer C++ /clr-Anwendung unter einer früheren Laufzeitversion
Sofern nicht anders angegeben, ist eine C++-Anwendung für .NET Framework darauf ausgelegt, auf der CLR-Version (Common Language Runtime) ausgeführt zu werden, die der Compiler zum Erstellen der Anwendung verwendet. Es ist jedoch möglich, dass eine EXE-Anwendung für eine Version der Runtime erstellt wurde, um auf allen anderen Versionen ausgeführt zu werden, die die erforderlichen Funktionen bereitstellen.  
  
 Stellen Sie eine App.Config-Datei bereit, die Runtimeversionsinformationen im Tag `supportedRuntime` enthält, um dies zu ermöglichen.  
  
 Zur Laufzeit muss die App.Config-Datei über einen Namen im Format *filename.ext*.config verfügen, wobei *filename.ext* den Namen der ausführbaren Datei beschreibt, die die Anwendung startet, und sie muss sich im gleichen Verzeichnis wie die ausführbare Datei befinden. Wenn Ihre Anwendung beispielsweise „TestApp.exe“ heißt, sollte der Name der App.Config-Datei „TestApp.exe.config“ sein.  
  
 Wenn Sie mehr als eine Runtimeversion angeben, und die Anwendung auf einem Computer ausgeführt wird, auf dem mehr als eine Runtimeversion installiert ist, verwendet die Anwendung die erste Version, die in der Konfigurationsdatei angegeben und installiert ist.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren einer App für die Ausrichtung auf eine .NET Framework-Version](https://msdn.microsoft.com/5247b307-89ca-417b-8dd0-e8f9bd2f4717).  
  
 Für die Ausführung auf Version 1.0 oder Version 1.1 der CLR muss eine Anwendung, die mit dem Visual C++-Compiler erstellt wurde, mithilfe von [/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)