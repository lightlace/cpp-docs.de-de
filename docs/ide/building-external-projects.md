---
title: Erstellen externer Projekte | Microsoft Docs
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
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="building-external-projects"></a>Erstellen externer Projekte
Ein externes Projekt ist ein Visual C++-Projekt, verwendet ein Makefile oder andere Einrichtungen, die außerhalb (Fremdschlüssel oder externe) sind, der Visual C++-Entwicklungsumgebung.  
  
 Wenn Sie ein externes Projekt (z. B. ein Makefile-Projekt), das Sie verwenden möchten verfügen, in der Visual C++-Entwicklungsumgebung erstellen, erstellen Sie ein Makefile-Projekt aus, und geben Sie des Projekts erstellen Sie Befehle und Ausgabe im Makefile-Anwendungs-Assistenten. Weitere Informationen finden Sie unter [Erstellen eines Makefile-Projekts](../ide/creating-a-makefile-project.md).  
  
 Beachten Sie, dass Visual C++ nicht mehr die Möglichkeit unterstützt, eine Makefile für das aktive Projekt in der Entwicklungsumgebung zu exportieren. Verwendung [Devenv-Befehlszeilenschalter](/visualstudio/ide/reference/devenv-command-line-switches) zum Erstellen von Visual Studio-Projekten in der Befehlszeile.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von C++-Projekten in Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)