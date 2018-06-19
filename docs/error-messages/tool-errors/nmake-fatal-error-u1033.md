---
title: 'NMAKE: Schwerwiegender Fehler U1033 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1d39d4c35ec66d405d51d601b7c5d2b2ab37b02
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319269"
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