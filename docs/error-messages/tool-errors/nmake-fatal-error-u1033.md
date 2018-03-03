---
title: 'NMAKE: Schwerwiegender Fehler U1033 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94f2626e1ce318d83d306595e386f880c62dec3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE: Schwerwiegender Fehler U1033
Syntaxfehler: 'Zeichenfolge' unerwartet  
  
 Die Zeichenfolge ist nicht Teil der gültige Syntax für ein Makefile.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Falls die schließende spitze Klammern (**<<**) für eine Inlinedatei sind nicht am Anfang einer Zeile, tritt der folgende Fehler auf:  
  
    ```  
    syntax error : 'EOF' unexpected  
    ```  
  
2.  Wenn eine Makrodefinition im Makefile ein Gleichheitszeichen enthält (**=**) ohne eine vorangestellte Namen, oder wenn der Name definiert wird, ist ein Makro, das nicht erweitert, tritt der folgende Fehler auf:  
  
    ```  
    syntax error : '=' unexpected  
    ```  
  
3.  Wenn das Semikolon (**;**) in einer Kommentarzeile an in-TOOLS. INI ist nicht am Anfang der Zeile, tritt der folgende Fehler auf:  
  
    ```  
    syntax error : ';' unexpected  
    ```  
  
4.  Wenn Sie die Makefile von einem Textverarbeitungsprogramm formatiert wurde, kann der folgende Fehler auftreten:  
  
    ```  
    syntax error : ':' unexpected  
    ```