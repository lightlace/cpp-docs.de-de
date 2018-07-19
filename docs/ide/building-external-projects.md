---
title: Erstellen externer Projekte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- external projects
- Visual C++ projects, external projects
- builds [C++], external projects
- projects [C++], external projects
- Makefile projects, external projects
ms.assetid: 650b7803-ea91-489d-bee3-8f3e990e223c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97b6aa1e5939afe55644df6529bf75ba043f20bb
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33330345"
---
# <a name="building-external-projects"></a>Erstellen externer Projekte
Ein externes Projekt ist ein Visual C++-Projekt, das ein Makefile oder andere Funktionen verwendet, die sich außerhalb (fremd oder extern) der Visual C++-Entwicklungsumgebung befinden.  
  
 Wenn Sie über ein externes Projekt verfügen (z.B. ein Makefile-Projekt), das in der Visual C++-Entwicklungsumgebung erstellt werden soll, erstellen Sie ein Makefile-Projekt, und geben Sie den Buildbefehl und die Ausgabe Ihres Projekts im Makefile-Anwendungs-Assistenten an. Weitere Informationen finden Sie unter [Creating a Makefile Project (Erstellen eines Makefile-Projekts)](../ide/creating-a-makefile-project.md).  
  
 Beachten Sie, dass Visual C++ das Exportieren eines Makefiles für das aktive Projekt der Entwicklungsumgebung nicht mehr unterstützt. Verwenden Sie [Devenv-Befehlszeilenoptionen](/visualstudio/ide/reference/devenv-command-line-switches), um Visual Studio-Projekte mit der Befehlszeile zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von C++-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)