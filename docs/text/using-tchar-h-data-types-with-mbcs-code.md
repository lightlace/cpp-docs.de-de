---
title: Verwenden von TCHAR. Datentypen mit _MBCS-Code H | Microsoft Docs
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e80ecd123e3fc47705563156e33f46ecd99a0321
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858353"
---
# <a name="using-tcharh-data-types-with-mbcs-code"></a>Verwenden von TCHAR.H-Datentypen in _MBCS-Code
Wenn die manifestkonstante **_MBCS** wird definiert, einen bestimmten generischen Textroutinen ist einem der folgenden Arten von Routinen:  
  
-   Eine SBCS-Routine, die ordnungsgemäß Multibytes, Zeichen und Zeichenfolgen verarbeitet. In diesem Fall werden die Zeichenfolgenargumente Typ erwartet **Char\***. Beispielsweise `_tprintf` ordnet `printf`; die Zeichenfolgenargumente auf `printf` sind vom Typ **Char\***. Bei Verwendung der **_TCHAR** Allgemeintext-Datentyp für die String-Typen, die die formale und tatsächliche Parametertypen für `printf` angepasst werden, weil **_TCHAR** \* ordnet **Char \***.  
  
-   Eine MBCS-spezifische Routine. In diesem Fall werden die Zeichenfolgenargumente Typ erwartet `unsigned` **Char\***. Beispielsweise `_tcsrev` ordnet `_mbsrev`, der erwartet, und gibt eine Zeichenfolge vom Typ `unsigned` **Char\***. Bei Verwendung der **_TCHAR** Allgemeintext-Datentyp für die Zeichenfolgen-Datentypen möglicherweise Konflikte Typ vorhanden ist, da **_TCHAR** Zuordnungen auf den Typ `char`.  
  
 Im Folgenden werden drei Lösungen vorgestellt, um einen solchen Typenkonflikt (und die daraus resultierenden C-Compilerwarnungen oder C++-Compilerfehler) zu verhindern:  
  
-   Verwendet das Standardverhalten. TCHAR.h stellt generische Textroutinen für die Routinen in die Laufzeitbibliotheken wie im folgenden Beispiel.  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     Im Standardfall den Prototyp für `_tcsrev` ordnet `_mbsrev` über ein Thunk in Libc.lib. Dadurch werden die Typen von der `_mbsrev` eingehende Parameter und ausgehende Rückgabewert aus **_TCHAR \***  (d. h. `char` **\***) zu `unsigned` `char` **\***. Diese Methode wird sichergestellt, dass bei Verwendung von übereinstimmenden Typ **_TCHAR**, aber es ist wegen des Verwaltungsaufwands für Funktion Aufruf relativ langsam.  
  
-   Verwenden Sie Inlinefunktionen, indem Sie die folgende Präprozessoranweisung in Ihren Code integrieren.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     Diese Methode verursacht eine Inline-Funktionsthunk, bereitgestellt in Tchar.h, generischen Textroutinen direkt an die entsprechende MBCS-Routine zuordnen. Im folgenden Codeauszug aus Tchar.h veranschaulicht, wie dies funktioniert.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     Wenn Sie Inlining verwenden können, ist dies die beste Lösung, da es Typübereinstimmung sicherstellt und keinen zusätzlichen Zeit- oder Kostenaufwand mit sich bringt.  
  
-   Verwenden Sie direkte Zuordnung durch Integrieren der Präprozessor folgenden Anweisung im Code.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Dieser Ansatz bietet eine schnelle Alternative, wenn Sie das Standardverhalten nicht verwenden möchten oder kein Inlining verwenden können. Es bewirkt, dass die generischen Textroutinen von einem Makro direkt an die MBCS-Version der Routine, wie im folgenden Beispiel aus Tchar.h zugeordnet werden.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     Wenn Sie diesen Ansatz verwenden, müssen Sie darauf achten, die Verwendung der entsprechenden Datentypen für Zeichenfolgenargumente und Rückgabewerte Zeichenfolge stellt sicher sein. Zum Sicherstellen einer ordnungsgemäßen Typübereinstimmung können Sie die Typumwandlung oder generischen Text des Datentyps **_TXCHAR** verwenden. **_TXCHAR** Zuordnungen auf den Typ `char` in SBCS-Code jedoch Zuordnungen auf den Typ `unsigned` `char` in MBCS-Code. Weitere Informationen über generische Textfunktion Makros finden Sie unter [Zuordnen von generischem Text](../c-runtime-library/generic-text-mappings.md) in der *Run-Time Library Reference*.  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md)