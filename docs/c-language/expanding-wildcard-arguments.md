---
title: Erweitern von Platzhalterargumenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69d7a9fc75e23a03e4db232bc798c89f89083e62
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383630"
---
# <a name="expanding-wildcard-arguments"></a>Erweitern von Platzhalterargumenten
**Microsoft-spezifisch**  
  
 Wenn Sie ein C-Programm ausführen, können Sie einen von zwei Platzhaltern – das Fragezeichen (?) und das Sternchen (*) – verwenden, um Dateinamen- und Pfadargumente in der Befehlszeile anzugeben.  
  
 Standardmäßig werden Platzhalter in Befehlszeilenargumenten nicht erweitert. Sie können den die normale `argv` -Laderoutine für den Argumentvektor durch eine Version ersetzen, die Platzhalter durch eine Verknüpfung mit der Datei „setargv.obj“ oder der Datei „wsetargv.obj“ erweitert. Wenn das Programm eine `main` -Funktion verwendet, stellen Sie eine Verknüpfung mit „setargv.obj“ her. Wenn das Programm eine `wmain` -Funktion verwendet, stellen Sie eine Verknüpfung mit „wsetargv.obj“ her. Beide weisen das gleiche Verhalten auf.  
  
 Um eine Verknüpfung mit „setargv.obj“ oder „wsetargv.obj“ herzustellen, verwenden Sie die **/link** -Option. Zum Beispiel:  
  
 **cl example.c /link setargv.obj**  
  
 Die Platzhalter werden auf dieselbe Weise wie Betriebssystembefehle erweitert. (Weitere Informationen erhalten Sie im Benutzerhandbuch des Betriebssystems, wenn Sie mit Platzhaltern nicht vertraut sind.)  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Linkoptionen](../c-runtime-library/link-options.md)   
 [main-Funktion und Programmausführung](../c-language/main-function-and-program-execution.md)