---
title: "__argc, __argv, __wargv"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "__wargv"
  - "__argv"
  - "__argc"
apilocation: 
  - "msvcrt120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__argv"
  - "__argc"
  - "__wargv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__argc"
  - "__argv"
  - "__wargv"
ms.assetid: 17001b0a-04ad-4762-b3a6-c54847f02d7c
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# __argc, __argv, __wargv
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die globale Variable `__argc` zählt die Anzahl von Befehlszeilenargumenten, die an das Programm übergeben werden.  `__argv` ist ein Zeiger auf ein Array mit Einzelbytezeichen oder Multibyte\-Zeichensätzen, die die Programmargumente enthalten, und `__wargv` ist ein Zeiger auf ein Array mit Breitzeichen\-Zeichenfolgen, die die Programmargumente enthalten.  Diese globalen Variablen stellen die Argumente für `main` oder `wmain` bereit.  
  
## Syntax  
  
```  
extern int __argc; extern char ** __argv; extern wchar_t ** __wargv;  
```  
  
## Hinweise  
 In einem Programm, das die Funktion `main` verwendet, werden  `__argc` und `__argv` beim Programmstart über die Befehlszeile initialisiert, die zum Starten des Programms verwendet wird.  Die Befehlszeile wird in einzelne Argumente analysiert, und Platzhalter werden erweitert.  Das Zählen der Argumente wird `__argc` zugewiesen, die Argumentzeichenfolgen werden auf dem Heap zugeordnet, und ein Zeiger zum Array der Argumente wird `__argv` zugewiesen.  In einem Programm, das für die Verwendung von Breitzeichen und einer `wmain`\-Funktion kompiliert ist, werden die Argumente analysiert und Platzhalter als Breitzeichen\-Zeichenfolgen erweitert. Außerdem wird ein Zeiger zum Array der Argumentzeichenfolgen zu `__wargv` zugewiesen.  
  
 Für portablen Code wird die Verwendung der an `main` übergebenen Argumente empfohlen, um die Befehlszeilenargumente in Ihrem Programm abzurufen.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE nicht definiert|\_UNICODE definiert|  
|----------------------|-------------------------------|-------------------------|  
|`__targv`|`__argv`|`__wargv`|  
  
## Anforderungen  
  
|Globale Variable|Erforderlicher Header|  
|----------------------|---------------------------|  
|`__argc`, `__argv`, `__wargv`|\<stdlib.h\>, \<cstdlib\> \(C\+\+\)|  
  
 `__argc`, `__argv` und `__wargv` sind Microsoft\-Erweiterungen.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Globale Variablen](../c-runtime-library/global-variables.md)   
 [main: Programmstart](../cpp/main-program-startup.md)   
 [Verwenden von "wmain" anstelle von "main"](../cpp/using-wmain-instead-of-main.md)