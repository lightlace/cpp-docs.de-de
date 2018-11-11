---
title: Ausführen einer C++- oder CLR-Anwendung in einer früheren Runtimeversion
ms.date: 11/04/2016
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
ms.openlocfilehash: effcda9de1cb1005855f5752060dc61e28dcebf4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581518"
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Ausführen einer C++ /clr-Anwendung in einer früheren Runtimeversion

Sofern nicht anders angegeben, ist eine C++-Anwendung für .NET Framework darauf ausgelegt, auf der CLR-Version (Common Language Runtime) ausgeführt zu werden, die der Compiler zum Erstellen der Anwendung verwendet. Es ist jedoch möglich, dass eine EXE-Anwendung für eine Version der Runtime erstellt wurde, um auf allen anderen Versionen ausgeführt zu werden, die die erforderlichen Funktionen bereitstellen.

Stellen Sie eine App.Config-Datei bereit, die Runtimeversionsinformationen im Tag `supportedRuntime` enthält, um dies zu ermöglichen.

Zur Laufzeit muss die App.Config-Datei über einen Namen im Format *filename.ext*.config verfügen, wobei *filename.ext* den Namen der ausführbaren Datei beschreibt, die die Anwendung startet, und sie muss sich im gleichen Verzeichnis wie die ausführbare Datei befinden. Wenn Ihre Anwendung beispielsweise „TestApp.exe“ heißt, sollte der Name der App.Config-Datei „TestApp.exe.config“ sein.

Wenn Sie mehr als eine Runtimeversion angeben, und die Anwendung auf einem Computer ausgeführt wird, auf dem mehr als eine Runtimeversion installiert ist, verwendet die Anwendung die erste Version, die in der Konfigurationsdatei angegeben und installiert ist.

## <a name="see-also"></a>Siehe auch

[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)