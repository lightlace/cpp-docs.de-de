---
title: Platzhaltererweiterung | Microsoft Docs
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
ms.openlocfilehash: bb58d5da479d686cac0d18c9d36e500bd6b5a632
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420645"
---
# <a name="wildcard-expansion"></a>Platzhaltererweiterung
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Sie können Platzhalter – das Fragezeichen (?) und das Sternchen (*) – verwenden, um Dateinamen- und Pfadargumente in der Befehlszeile anzugeben.  
  
 Befehlszeilenargumente werden durch eine Routine aufgerufen behandelt **_setargv** (oder **_wsetargv** in der Breitzeichen-Umgebung), wird standardmäßig erweitert nicht Platzhalter in separate Zeichenfolgen im die `argv`Array von Zeichenfolgen. Weitere Informationen zum Aktivieren der platzhaltererweiterung finden Sie unter [Erweitern von Platzhalter-Argumenten](../c-language/expanding-wildcard-arguments.md).  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)