---
title: Veraltete Formen von Funktionsdeklarationen und -definitionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- old style function declarations
ms.assetid: 67c5038f-0529-4f29-9d0f-c27580977b50
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.openlocfilehash: 7ef80d6a438118da00d8afaf67cf9317cc50b953
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="obsolete-forms-of-function-declarations-and-definitions"></a>Veraltete Formen von Funktionsdeklarationen und -definitionen
Die Funktionsdeklarationen und -definitionen im alten Stil verwenden etwas andere Regeln für das Deklarieren von Parametern als die im ANSI-Standard empfohlene C-Syntax. Erstens besitzen die Deklarationen im alten Stil keine Parameterliste. Zweitens werden die Parameter in der Funktionsdefinition aufgeführt, allerdings werden ihre Typen nicht in der Parameterliste deklariert. Die Typdeklarationen gehen der Verbundanweisung voran, die den Funktionsrumpf bildet. Der alte Syntaxstil ist hinfällig und sollte im neuen Code nicht mehr verwendet werden. Code mit der alten Syntax wird jedoch weiterhin unterstützt. Dieses Beispiel veranschaulicht die veralteten Formen von Deklarationen und Definitionen:  
  
```  
double old_style();           /* Obsolete function declaration */  
  
double alt_style( a , real )  /* Obsolete function definition */  
    double *real;   
    int a;   
{  
    return ( *real + a ) ;  
}  
```  
  
 Die Funktionen, die eine ganze Zahl oder einen Zeiger mit derselben Größe wie `int` zurückgeben, müssen keine Deklaration haben, obwohl die Deklaration empfohlen wird.  
  
 Um die Einhaltung des ANSI-C-Standards zu gewährleisten, generieren Funktionsdeklarationen alten Stils mit Auslassungszeichen jetzt beim Kompilieren mit der /Za-Option einen Fehler. Beim Kompilieren mit "/Ze" wird eine Warnung der Stufe 4 generiert. Zum Beispiel:  
  
```  
void funct1( a, ... )  /* Generates a warning under /Ze or */  
int a;                 /* an error when compiling with /Za */  
{  
}  
```  
  
 Sie sollten diese Deklaration als Prototyp neu schreiben:  
  
```  
void funct1( int a, ... )  
{  
}  
```  
  
 Funktionsdeklarationen im alten Stil generieren außerdem Warnungen, wenn Sie danach die gleiche Funktion entweder mit Auslassungszeichen oder einem Parameter mit einem Typ deklarieren oder definieren, der nicht der gleiche ist wie sein höhergestufter Typ.  
  
 Im nächsten Abschnitt [C-Funktionsdefinitionen](../c-language/c-function-definitions.md) wird die Syntax von Funktionsdefinitionen aufgezeigt, einschließlich des alten Syntaxstils. Das Nichtterminal für die Parameterliste im alten Syntaxstil ist *identifier-list*.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Funktionen](../c-language/overview-of-functions.md)
