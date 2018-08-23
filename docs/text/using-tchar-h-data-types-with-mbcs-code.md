---
title: Verwenden von TCHAR. H-Datentypen in _MBCS-Code | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- tchar.h
- TCHAR
dev_langs:
- C++
helpviewer_keywords:
- mapping generic-text
- generic-text data types [C++]
- generic-text mappings [C++]
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 445e4c9e5c3c7a71d527b6a378cad9e1d767354a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604730"
---
# <a name="using-tcharh-data-types-with-mbcs-code"></a>Verwenden von TCHAR.H-Datentypen in _MBCS-Code
Wenn die manifestkonstante `_MBCS` wird definiert, eine bestimmte generische Textroutine einer der folgenden Arten von Routinen zugeordnet:  
  
-   Eine SBCS-Routine, die ordnungsgemäß Multibytes, Zeichen und Zeichenfolgen verarbeitet. In diesem Fall werden Zeichenfolgenargumente vom Typ `char*` erwartet. Beispielsweise wird `_tprintf` `printf` zugeordnet; die Zeichenfolgenargumente für `printf` sind vom Typ `char*`. Wenn Sie generischen Text vom Datentyp `_TCHAR` für Ihre Zeichenfolgentypen verwenden, stimmen die formalen und tatsächlichen Parametertypen für `printf` überein, da `_TCHAR*` `char*` zugeordnet wird.  
  
-   Eine MBCS-spezifische Routine. In diesem Fall werden Zeichenfolgenargumente vom Typ `unsigned char*` erwartet. Beispielsweise wird `_tcsrev` `_mbsrev` zugeordnet, wobei eine Zeichenfolge vom Typ `unsigned char*` erwartet und zurückgegeben wird. Bei Verwendung der `_TCHAR` generischen Text vom Datentyp für Ihre Zeichenfolgentypen verwenden, es liegt ein Typkonflikt `_TCHAR` wird Typ `char`.  
  
 Im Folgenden werden drei Lösungen vorgestellt, um einen solchen Typenkonflikt (und die daraus resultierenden C-Compilerwarnungen oder C++-Compilerfehler) zu verhindern:  
  
-   Verwendet das Standardverhalten. TCHAR.h enthält generische Textroutinen für Routinen in Laufzeitbibliotheken, wie im folgenden Beispiel gezeigt.  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     Im Standardfall wird der Prototyp für `_tcsrev` ordnet `_mbsrev` über einen Thunk in Libc.lib. Dadurch werden die Typen von der `_mbsrev` eingehende-Parameter und der ausgehende Rückgabewert aus `_TCHAR*` (d. h. `char *`) zu `unsigned char *`. Diese Methode stellt typübereinstimmung bei Verwendung von sicher `_TCHAR`, aber es ist relativ gering aufgrund des Mehraufwands für den Funktionsaufruf.  
  
-   Verwenden Sie Inlinefunktionen, indem Sie die folgende Präprozessoranweisung in Ihren Code integrieren.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     Diese Methode verursacht eine Inline-Funktionsthunk, bereitgestellt in Tchar.h, um die generische Textroutine direkt der entsprechenden MBCS-Routine zuzuordnen. Im folgenden Codeauszug aus Tchar.h enthält ein Beispiel wie dies vonstatten geht.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     Wenn Sie Inlining verwenden können, ist dies die beste Lösung, da es Typübereinstimmung sicherstellt und keinen zusätzlichen Zeit- oder Kostenaufwand mit sich bringt.  
  
-   Verwenden Sie direkte Zuordnung, indem Sie die folgende präprozessoranweisung in Ihren Code integrieren.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Dieser Ansatz bietet eine schnelle Alternative, wenn Sie das Standardverhalten nicht verwenden möchten oder kein Inlining verwenden können. Es bewirkt, dass die generische Textroutine direkt an die MBCS-Version der Routine, wie im folgenden Beispiel aus TCHAR.h gezeigt von einem Makro zugeordnet werden.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     Wenn Sie diesen Ansatz verwenden, müssen Sie sorgfältig, um sicherzustellen, dass die Verwendung der entsprechenden Datentypen für Zeichenfolgenargumente und-Rückgabewerte sein. Um eine ordnungsgemäße Typübereinstimmung sicherzustellen, können Sie die Typumwandlung oder generischen Text vom Datentyp `_TXCHAR` verwenden. `_TXCHAR` wird Typ **Char** in SBCS-Code zugeordnet, jedoch Typ **unsigned Char** in MBCS-Code. Weitere Informationen zu generischen Textmakros finden Sie unter [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md) in die *Run-Time Library Reference*.  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md)