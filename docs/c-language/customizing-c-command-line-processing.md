---
title: Anpassen der C-Befehlszeilenverarbeitung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.assetid: c20fa11d-b35b-4f3e-93b6-2cd5a1c3c993
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 824de86ec0930fb93bf5fa0a2a8ac15a4237e4fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="customizing-c-command-line-processing"></a>Anpassen der C-Befehlszeilenverarbeitung
Wenn das Programm keine Befehlszeilenargumente akzeptiert, können Sie ein wenig Platz sparen, indem Sie die Verwendung der Bibliotheksroutine unterdrücken, die die Befehlszeilenverarbeitung ausführt. Diese Routine hat die Bezeichnung **_setargv** (oder **_wsetargv** in Umgebungen aus Zeichenfolgen mit Breitzeichen), wie unter [Erweitern von Platzhalter-Argumenten](../c-language/expanding-wildcard-arguments.md) beschrieben. Um ihre Verwendung zu unterdrücken, definieren Sie eine Routine, die in der Datei mit der **main**-Funktion keine Aktion ausführt, und nennen Sie diese **_setargv** (oder **_wsetargv** in Umgebungen aus Zeichenfolgen mit Breitzeichen). Der Aufruf von **_setargv** oder **_wsetargv** wird dann durch Ihre Definition von **_setargv** oder **_wsetargv** erfüllt, und die Bibliotheksversion wird nicht geladen.  
  
 Auch wenn Sie niemals auf die Umgebungstabelle vom `envp`-Argument aus zugreifen, können Sie anstelle der umgebungsverarbeitenden Routine **_setenvp** (oder **_wsetenvp**) eine eigene leere Routine bereitstellen.  
  
 Wenn Ihr Programm die **_spawn**- oder **_exec**-Familie von Routinen in der C-Laufzeitbibliothek aufruft, sollten Sie die umgebungsverarbeitende Routine nicht unterdrücken, da mit ihr eine Umgebung aus dem erzeugenden Prozess an den neuen Prozess übergeben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [main-Funktion und Programmausführung](../c-language/main-function-and-program-execution.md)