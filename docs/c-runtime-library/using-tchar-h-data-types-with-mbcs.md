---
title: Verwenden von TCHAR.H-Datentypen mit _MBCS | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- TCHAR.H data types
- MBCS data type
- _MBCS data type
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: ec4f2b6245e024541a0247ebafbabc534ba9ded4
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="using-tcharh-data-types-with-mbcs"></a>Verwenden von TCHAR.H-Datentypen mit _MBCS
**Microsoft-spezifisch**  
  
 Wie aus die Tabelle mit den Zuordnungen für generische Textroutinen hervorgeht (siehe [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md)), wird eine bestimmte generische Textroutine einer der folgenden Arten von Routinen zugeordnet, wenn die Manifestkonstante `_MBCS` definiert ist:  
  
-   Eine SBCS-Routine, die ordnungsgemäß Multibytes, Zeichen und Zeichenfolgen verarbeitet. In diesem Fall werden Zeichenfolgenargumente vom Typ `char*` erwartet. Beispielsweise wird `_tprintf` `printf` zugeordnet; die Zeichenfolgenargumente für `printf` sind vom Typ `char*`. Wenn Sie generischen Text vom Datentyp `_TCHAR` für Ihre Zeichenfolgentypen verwenden, stimmen die formalen und tatsächlichen Parametertypen für `printf` überein, da `_TCHAR*` `char*` zugeordnet wird.  
  
-   Eine MBCS-spezifische Routine. In diesem Fall werden Zeichenfolgenargumente vom Typ `unsigned char*` erwartet. Beispielsweise wird `_tcsrev` `_mbsrev` zugeordnet, wobei eine Zeichenfolge vom Typ `unsigned char*` erwartet und zurückgegeben wird. Wenn Sie erneut den generischen Text vom Datentyp `_TCHAR` für Ihre Zeichenfolgentypen verwenden, kommt es möglicherweise zu einem Typenkonflikt, da `_TCHAR` Typ `char` zugeordnet wird.  
  
 Im Folgenden werden drei Lösungen vorgestellt, um einen solchen Typenkonflikt (und die daraus resultierenden C-Compilerwarnungen oder C++-Compilerfehler) zu verhindern:  
  
-   Verwendet das Standardverhalten. TCHAR.H enthält Prototypen von generischen Textroutinen für Routinen in Laufzeitbibliotheken, wie im folgenden Beispiel gezeigt wird.  
  
    ```  
    char *_tcsrev(char *);  
    ```  
  
     Im Standardfall wird der Prototyp für `_tcsrev` über einen Thunk in LIBC.LIB `_mbsrev` zugeordnet. Dadurch werden die Typen der eingehenden `_mbsrev`-Parameter und der ausgehende Rückgabewert aus `_TCHAR *` (z.B. `char *`) in `unsigned char *` geändert. Diese Methode stellt Typübereinstimmung bei Verwendung von `_TCHAR` sicher, ist aufgrund des Funktionsaufrufsoverheads jedoch relativ langsam.  
  
-   Verwenden Sie Inlinefunktionen, indem Sie die folgende Präprozessoranweisung in Ihren Code integrieren.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     Diese Methode verursacht einen Inlinefunktionsthunk in TCHAR.H, um die generische Textroutine direkt der entsprechenden MBCS-Routine zuzuordnen. Mit dem folgenden Codeauszug aus TCHAR.H wird ein einfaches Beispiel für diesen Vorgang gezeigt.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     Wenn Sie Inlining verwenden können, ist dies die beste Lösung, da es Typübereinstimmung sicherstellt und keinen zusätzlichen Zeit- oder Kostenaufwand mit sich bringt.  
  
-   Verwenden Sie die direkte Zuordnung, indem Sie die folgende Präprozessoranweisung in Ihren Code integrieren.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Dieser Ansatz bietet eine schnelle Alternative, wenn Sie das Standardverhalten nicht verwenden möchten oder kein Inlining verwenden können. Es bewirkt, dass die durch ein Makro zuzuordnende generische Textroutine direkt der MBCS-Version der Routine zugeordnet wird, wie im folgenden Beispiel aus TCHAR.H gezeigt wird.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
 Wenn Sie diesen Ansatz verwenden, müssen Sie in jedem Fall sicherstellen, dass die entsprechenden Datentypen für Zeichenfolgenargumente und -rückgabewerte verwendet werden. Um eine ordnungsgemäße Typübereinstimmung sicherzustellen, können Sie die Typumwandlung oder generischen Text vom Datentyp `_TXCHAR` verwenden. `_TXCHAR` wird Typ `char` im SBCS-Code zugeordnet, jedoch Typ `unsigned char` im MBCS-Code. Weitere Informationen zu generischen Textmakros finden Sie unter [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
