---
title: Anpassen der C++-Befehlszeilenverarbeitung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _setenvp
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e2691ba3b83cd536c6f0a152bf4de2a855f81e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="customizing-c-command-line-processing"></a>Anpassen der C++-Befehlszeilenverarbeitung
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Wenn das Programm keine Befehlszeilenargumente akzeptiert, können Sie ein wenig Platz sparen, indem Sie die Verwendung der Bibliotheksroutine unterdrücken, die die Befehlszeilenverarbeitung ausführt. Diese Routine hat die Bezeichnung **_setargv** und wird im beschrieben [Platzhaltererweiterung](../cpp/wildcard-expansion.md). Um seine Verwendung zu unterdrücken, definieren Sie eine Routine, "nothing" in der Datei mit den **main** -Funktion, und nennen Sie sie **_setargv**. Der Aufruf von **_setargv** erfüllt wird dann durch Ihre Definition von **_setargv**, und die Bibliotheksversion wird nicht geladen.  
  
 Ebenso sollten Sie nie auf die umgebungstabelle zugreifen der `envp` Argument, Sie können eine eigene leere Routine anstelle von bereitstellen **_setenvp**, die umgebungsverarbeitende Routine. Wie bei der **_setargv** Funktion **_setenvp** muss deklariert werden, als **"extern"C""**.  
  
 Das Programm möglicherweise Aufrufe an die **Spawn** oder `exec` -Gruppe von Routinen in C-Laufzeitbibliothek. Wenn dies der Fall ist, sollten Sie die umgebungsverarbeitende Routine nicht unterdrücken, da diese Routine verwendet wird, um eine Umgebung aus dem übergeordneten Prozess an den untergeordneten Prozess zu übergeben.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)