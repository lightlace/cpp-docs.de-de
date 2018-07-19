---
title: Platzhaltererweiterung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line [C++], processing arguments
- command line [C++], wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f4de54cbbe978534a42dcb9cbfa677eb1597aa5
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939135"
---
# <a name="wildcard-expansion"></a>Platzhaltererweiterung
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Sie können Platzhalter – das Fragezeichen (?) und das Sternchen (*) – verwenden, um Dateinamen- und Pfadargumente in der Befehlszeile anzugeben.  
  
 Befehlszeilenargumente werden durch eine Routine, die mit dem Namen behandelt `_setargv` (oder `_wsetargv` in der Breitzeichen-Umgebung), die standardmäßig Platzhalter in separate Zeichenfolgen im nicht erweitert die `argv` Zeichenfolgenarray. Weitere Informationen zum Aktivieren von platzhaltererweiterung finden Sie unter [Erweitern von Platzhalterargumenten](../c-language/expanding-wildcard-arguments.md).  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)