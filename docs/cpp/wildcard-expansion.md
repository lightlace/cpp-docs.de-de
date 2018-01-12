---
title: Platzhaltererweiterung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _setargv
dev_langs: C++
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line [C++], processing arguments
- command line [C++], wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c9bbb5dcc706e08b2b985769248969f9bd23201
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wildcard-expansion"></a>Platzhaltererweiterung
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Sie können Platzhalter – das Fragezeichen (?) und das Sternchen (*) – verwenden, um Dateinamen- und Pfadargumente in der Befehlszeile anzugeben.  
  
 Befehlszeilenargumente werden durch eine Routine aufgerufen behandelt **_setargv** (oder **_wsetargv** in der Breitzeichen-Umgebung), wird standardmäßig erweitert nicht Platzhalter in separate Zeichenfolgen im die `argv`Array von Zeichenfolgen. Weitere Informationen zum Aktivieren der platzhaltererweiterung finden Sie unter [Erweitern von Platzhalter-Argumenten](../c-language/expanding-wildcard-arguments.md).  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)