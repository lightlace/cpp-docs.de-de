---
title: "__crtLCMapStringW"
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
  - "__crtLCMapStringW"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__crtLCMapStringW"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__crtLCMapStringW"
ms.assetid: 45b4ac0e-438c-4fa3-b4d1-34195f4467d9
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# __crtLCMapStringW
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ordnet eine Zeichenfolge einer anderen zu, wobei eine angegebene Gebietsschema\-abhängige Umwandlung durchgeführt wird. Mit dieser Funktion kann auch ein Sortierschlüssel für die Eingabezeichenfolge generiert werden.  
  
## Syntax  
  
```cpp  
int __crtLCMapStringW(  
   LCID    Locale,  
   DWORD   dwMapFlags,  
   LPCWSTR lpSrcStr,  
   int     cchSrc,  
   LPWSTR  lpDestStr,  
   int     cchDest)  
```  
  
#### Parameter  
 `Locale`  
 Gebietsschemabezeichner Das Gebietsschema stellt einen Kontext für die Zeichenfolgenzuordnung oder zum Generieren des Sortierschlüssels bereit. Eine Anwendung kann mithilfe des `MAKELCID`\-Makros einen Gebietsschemabezeichner generieren.  
  
 `dwMapFlags`  
 Der Typ der Transformation, der während der Zeichenfolgenzuordnung oder des Generierens des Sortierschlüssels verwendet werden soll.  
  
 `lpSrcStr`  
 Zeiger auf eine Quellzeichenfolge, die die Funktion zuordnet oder für die Sortierschlüsselgenerierung verwendet. Für diesen Parameter wird davon ausgegangen, dass es sich um eine Unicode\-Zeichenfolge handelt.  
  
 `cchSrc`  
 Auf die Größe, in Zeichen, der Zeichenfolge wird mit dem `lpSrcStr`\-Parameter verwiesen. Diese Anzahl kann den NULL\-Terminator enthalten, muss jedoch nicht.  
  
 Ein `cchSrc`\-Wert von –1 gibt an, dass die Zeichenfolge, auf die von `lpSrcStr` verwiesen wird, null\-terminiert ist. Wenn dies der Fall ist und diese Funktion im Zeichenfolgenzuordnungsmodus verwendet wird, berechnet die Funktion die Länge der Zeichenfolge selbst und lässt die zugeordnete Zeichenfolge, die in `*lpDestStr` gespeichert wird, auf Null enden.  
  
 `lpDestStr`  
 Long\-Zeiger auf einen Puffer, in den die Funktion die zugeordnete Zeichenfolge oder den Sortierschlüssel speichert.  
  
 `cchDest`  
 Größe, in Zeichen, des Puffers, auf die von `lpDestStr` verwiesen wird.  
  
## Rückgabewert  
 Wenn der Wert von `cchDest` ungleich NULL ist, zeigt die Anzahl der Zeichen oder Bytes, wenn `LCMAP_SORTKEY` angegeben ist, die in den Puffer geschrieben wird, Erfolg an. Diese Anzahl bietet Platz für einen NULL\-Terminator.  
  
 Wenn der Wert von `cchDest` 0 ist, gibt Größe des Puffers in Zeichen oder Bytes, wenn `LCMAP_SORTKEY` angegeben ist, Erfolg an, was erforderlich für den Empfang der übersetzten Zeichenfolge oder des Sortierschlüssels ist. Diese Größe bietet Platz für einen NULL\-Terminator.  
  
 Null weist auf einen Fehler hin. Rufen Sie für erweiterte Fehlerinformationen die `GetLastError`\-Funktion auf.  
  
## Hinweise  
 Wenn `cchSrc` größer als 0 \(null\) ist und `lpSrcStr` ist eine Null\-terminierte Zeichenfolge, legt `__crtLCMapStringW``cchSrc` auf die Länge der Zeichenfolge fest.`__crtLCMapStringW` ruft dann die Breitzeichen\-Version \(Unicode\) der `LCMapString`\-Funktion mit den angegebenen Parametern auf. Weitere Informationen zu den Parametern und Rückgabewerten dieser Funktion finden Sie unter der `LCMapString`\-Funktion der [MSDN Library](http://go.microsoft.com/fwlink/?linkID=150542).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_\_crtLCMapStringW|awint.h|