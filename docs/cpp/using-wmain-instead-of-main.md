---
title: Mithilfe von "wmain" anstelle von Main | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- wmain
dev_langs:
- C++
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ef24360507c3c58d2c0839f780062340f8d7654f
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="using-wmain-instead-of-main"></a>Verwenden von "wmain" anstelle von "main"
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Im Unicode-Programmiermodell können Sie eine Breitzeichenversion der **main**-Funktion definieren. Verwendung **"wmain"** anstelle von **main** sollten Sie portablen Code schreiben, die die Unicode-Spezifikation entspricht.  
  
 Sie deklarieren die formalen Parameter für **wmain** unter Verwendung eines ähnlichen Formats wie für **main**. Sie können anschließend Breitzeichen-Argumente und optional einen Breitzeichen-Umgebungszeiger übergeben, der auf das Programm verweist. Der `argv`-Parameter und der `envp`-Parameter, die auf **wmain** verweisen, sind vom Typ `wchar_t*`.  
  
 Wenn Ihre Anwendung verwendet ein **main** -Funktion, die Mehrbyte-zeichenumgebung wird vom Betriebssystem beim Programmstart erstellt. Eine Breitzeichen-Kopie der Umgebung wird nur bei Bedarf erstellt (z. B. durch einen Aufruf der [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) oder [_wputenv](../c-runtime-library/reference/putenv-wputenv.md) Funktionen). Wenn bereits eine MBCS-Umgebung vorhanden ist, wird beim ersten Aufruf von `_wputenv` oder beim ersten Aufruf von `_wgetenv` eine entsprechende Breitzeichen-Zeichenfolgenumgebung erstellt. Auf diese Umgebung zeigt dann die globale Variable `_wenviron`, die eine Breitzeichenversion der globalen Variablen `_environ` ist. Zu diesem Zeitpunkt sind zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden und werden während der Lebensdauer des Programms vom Betriebssystem verwaltet.  
  
 Auf ähnliche Weise, wenn Ihre Anwendung verwendet ein **"wmain"** -Funktion, eine Umgebung MBCS (ASCII) wird beim ersten Aufruf von erstellt `_putenv` oder `getenv`, und verweist die `_environ` (globale Variable).  
  
 Weitere Informationen zur MBCS-Umgebung, finden Sie unter [Einzelbyte- und Mehrbyte-Zeichensätze](../c-runtime-library/single-byte-and-multibyte-character-sets.md) in die *Run-Time Library Reference.*  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)
