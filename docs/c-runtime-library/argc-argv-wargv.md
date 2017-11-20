---
title: __argc, __argv, __wargv | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __wargv
- __argv
- __argc
apilocation: msvcrt120.dll
apitype: DLLExport
f1_keywords:
- __argv
- __argc
- __wargv
dev_langs: C++
helpviewer_keywords:
- __argv
- __wargv
- __argc
ms.assetid: 17001b0a-04ad-4762-b3a6-c54847f02d7c
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dbb6e0886844cda7142ee52fcb545e122c38ea8e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="argc-argv-wargv"></a>__argc, __argv, __wargv
Die globale Variable `__argc` zählt die Anzahl von Befehlszeilenargumenten, die an das Programm übergeben werden. `__argv` ist ein Zeiger auf ein Array mit Einzelbytezeichen oder Multibyte-Zeichensätzen, die die Programmargumente enthalten, und `__wargv` ist ein Zeiger auf ein Array mit Breitzeichen-Zeichenfolgen, die die Programmargumente enthalten. Diese globalen Variablen stellen die Argumente für `main` oder `wmain` bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
extern int __argc;  
extern char ** __argv;  
extern wchar_t ** __wargv;  
```  
  
## <a name="remarks"></a>Hinweise  
 In einem Programm, das die Funktion `main` verwendet, werden `__argc` und `__argv` beim Programmstart über die Befehlszeile initialisiert, die zum Starten des Programms verwendet wird. Die Befehlszeile wird in einzelne Argumente analysiert, und Platzhalter werden erweitert. Das Zählen der Argumente wird `__argc` zugewiesen, die Argumentzeichenfolgen werden auf dem Heap zugeordnet, und ein Zeiger zum Array der Argumente wird `__argv` zugewiesen. In einem Programm, das für die Verwendung von Breitzeichen und einer `wmain`-Funktion kompiliert ist, werden die Argumente analysiert und Platzhalter als Breitzeichen-Zeichenfolgen erweitert. Außerdem wird ein Zeiger zum Array der Argumentzeichenfolgen zu `__wargv` zugewiesen.  
  
 Für portablen Code wird die Verwendung der an `main` übergebenen Argumente empfohlen, um die Befehlszeilenargumente in Ihrem Programm abzurufen.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE nicht definiert|_UNICODE definiert|  
|---------------------|---------------------------|-----------------------|  
|`__targv`|`__argv`|`__wargv`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Globale Variable|Erforderlicher Header|  
|---------------------|---------------------|  
|`__argc`, `__argv`, `__wargv`|\<stdlib.h>, \<cstdlib> (C++)|  
  
 `__argc`, `__argv` und `__wargv` sind Microsoft-Erweiterungen. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Globale Variablen](../c-runtime-library/global-variables.md)   
 [main: Programmstart](../cpp/main-program-startup.md)   
 [Verwenden von "wmain" anstelle von "main"](../cpp/using-wmain-instead-of-main.md)