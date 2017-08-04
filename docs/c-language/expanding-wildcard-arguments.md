---
title: Erweitern von Platzhalterargumenten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: c52c5734127e33a49ae57e9da279e4ef09798232
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

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
