---
title: Anpassen der C++-Befehlszeilenverarbeitung | Microsoft-Dokumentation
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
ms.openlocfilehash: 9415073630505e3cc879f53de14ed469c7e0e2ba
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939051"
---
# <a name="customizing-c-command-line-processing"></a>Anpassen der C++-Befehlszeilenverarbeitung
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Wenn das Programm keine Befehlszeilenargumente akzeptiert, können Sie ein wenig Platz sparen, indem Sie die Verwendung der Bibliotheksroutine unterdrücken, die die Befehlszeilenverarbeitung ausführt. Diese Routine hat die Bezeichnung `_setargv` und wird im beschrieben [Platzhaltererweiterung](../cpp/wildcard-expansion.md). Um ihre Verwendung zu unterdrücken, definieren Sie eine Routine, "nothing" in der Datei mit den `main` funktionieren, und nennen Sie sie `_setargv`. Der Aufruf von `_setargv` erfüllt wird dann durch Ihre Definition von `_setargv`, und die Bibliotheksversion wird nicht geladen werden.  
  
 Auf ähnliche Weise, wenn Sie niemals auf die umgebungstabelle auf die `envp` -Argument, Sie können Ihre eigene leere Routine anstelle der zu verwendende bereitstellen `_setenvp`, die umgebungsverarbeitende Routine. Wie bei der `_setargv` Funktion `_setenvp` muss deklariert werden, als **Extern "C"**.  
  
 Das Programm möglicherweise Aufrufe an die `spawn` oder `exec` -Gruppe von Routinen in der C-Laufzeitbibliothek. Wenn dies der Fall ist, sollten Sie die umgebungsverarbeitende Routine nicht unterdrücken, da diese Routine verwendet wird, um eine Umgebung aus dem übergeordneten Prozess an den untergeordneten Prozess zu übergeben.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)