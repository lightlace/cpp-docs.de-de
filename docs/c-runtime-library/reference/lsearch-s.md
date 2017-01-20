---
title: "_lsearch_s"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_lsearch_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_lsearch_s"
  - "lsearch_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lsearch_s-Funktion"
  - "Arrays [CRT], Suchen"
  - "Schlüssel, Suchen in Arrays"
  - "Lineares Suchen"
  - "lsearch_s-Funktion"
  - "Suchen, Linear"
  - "Werte, Suchen nach"
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# _lsearch_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt eine lineare Suche für einen Wert aus.  Eine Version von [\_lsearch](../../c-runtime-library/reference/lsearch.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
void *_lsearch_s(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### Parameter  
 `key`  
 Planen Sie für Suche für ein.  
  
 `base`  
 Zeiger zur Basis des zu durchsuchenden Arrays.  
  
 `num`  
 Anzahl der Elemente.  
  
 `size`  
 Größe jedes Arrayelements in Bytes.  
  
 `compare`  
 Zeiger auf die Vergleichsroutine.  Der zweite Parameter ist ein Zeiger auf die Schlüssel für die Suche.  Der dritte Parameter ist ein Zeiger auf ein mit der Schlüssel verglichen werden Arrayelement.  
  
 `context`  
 Ein Zeiger auf ein Objekt, auf das möglicherweise in der Vergleichsfunktion zugegriffen wird.  
  
## Rückgabewert  
 Wenn `key` gefunden wird, gibt `_lsearch_s`  einen Zeiger auf das Element des Arrays bei diesem `base` Entspricht `key` zurück.  Wenn `key` nicht gefunden wird, gibt `_lsearch_s`  einen Zeiger auf das neu hinzugefügten Element am Ende des Arrays zurück.  
  
 Wenn ungültige Parameter an die Funktion übergeben werden, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, wird `errno`  auf `EINVAL` festgelegt und die Funktion gibt `NULL` zurück.  Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### Fehlerbedingungen  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|0 \(Null\)|`EINVAL`|  
|any|any|`NULL`|an|any|`EINVAL`|  
  
## Hinweise  
 Die `_lsearch_s`\-Funktion führt eine lineare Suche für den Wert `key` in einem `num` \- Array Elemente, jedes von `width` Bytes aus.  Anders als `bsearch_s` erfordert `_lsearch_s` das Array nicht sortiert werden.  Wenn `key` nicht gefunden wird, wird `_lsearch_s` dem Ende des Arrays hinzu und inkrementiert `num`.  
  
 Die Funktion `compare` ist ein Zeiger auf eine vom Benutzer bereitgestellten Routine, die zwei Arrayelemente verglichen und einen Wert zurückgibt, der die Beziehung angibt.  Die Funktion `compare` verfügt auch den Zeiger Kontext als das erste Argument.  `_lsearch_s` ruft `compare` mindestens einmal während der Suche auf und übergibt Zeiger zu zwei Arrayelementen auf jedem Aufruf.  `compare` muss über Elemente vergleichen und entweder dem Wert ungleich 0 \(null\) \(die Elemente sind signifikant Sie unterscheiden\) oder 0 zurückgeben \(anschließend die Elemente signifikant, befinden\) identisch.  
  
 Der `context` Zeiger kann nützlich sein, wenn die gesuchte Datenstruktur Teil eines Objekts ist und die `compare`\-Funktion Member des Objekts zugreifen muss.  Beispielsweise kann Code in der `compare`\-Funktion den void\-Zeiger in die entsprechenden Objekttypen aufgelistet umwandeln und Member dieses Objekts zugreifen.  Die hinzugefügten `context` des Zeigers macht `_lsearch_s` sicherer, da zusätzliche Kontext verwendet werden kann, um die Reentranzfehler zu vermeiden, die mithilfe von statischen Variablen, um Daten zur Verfügung stehen die `compare`\-Funktion zugeordnet sind.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_lsearch_s`|\<search.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Suchen und Sortieren](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lfind\_s](../../c-runtime-library/reference/lfind-s.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)