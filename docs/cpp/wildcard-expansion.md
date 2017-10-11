---
title: Platzhaltererweiterung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 779a788cae6523a48a82694e55edf3c1da5519d7
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="wildcard-expansion"></a>Platzhaltererweiterung
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Sie können Platzhalter – das Fragezeichen (?) und das Sternchen (*) – verwenden, um Dateinamen- und Pfadargumente in der Befehlszeile anzugeben.  
  
 Befehlszeilenargumente werden durch eine Routine aufgerufen behandelt **_setargv** (oder **_wsetargv** in der Breitzeichen-Umgebung), wird standardmäßig erweitert nicht Platzhalter in separate Zeichenfolgen im die `argv`Array von Zeichenfolgen. Weitere Informationen zum Aktivieren der platzhaltererweiterung finden Sie unter [Erweitern von Platzhalter-Argumenten](../c-language/expanding-wildcard-arguments.md).  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)
