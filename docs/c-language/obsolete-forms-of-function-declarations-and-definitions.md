---
title: "Veraltete Formen von Funktionsdeklarationen und -definitionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Funktionsdeklarationen im alten Stil"
ms.assetid: 67c5038f-0529-4f29-9d0f-c27580977b50
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Veraltete Formen von Funktionsdeklarationen und -definitionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Funktionsdeklarationen und \-definitionen im alten Stil verwenden etwas andere Regeln für das Deklarieren von Parametern als die im ANSI\-Standard empfohlene C\-Syntax.  Erstens besitzen die Deklarationen im alten Stil keine Parameterliste.  Zweitens werden die Parameter in der Funktionsdefinition aufgeführt, allerdings werden ihre Typen nicht in der Parameterliste deklariert.  Die Typdeklarationen gehen der Verbundanweisung voran, die den Funktionsrumpf bildet.  Der alte Syntaxstil ist hinfällig und sollte im neuen Code nicht mehr verwendet werden.  Code mit der alten Syntax wird jedoch weiterhin unterstützt.  Dieses Beispiel veranschaulicht die veralteten Formen von Deklarationen und Definitionen:  
  
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
  
 Um die Einhaltung des ANSI\-C\-Standards zu gewährleisten, generieren Funktionsdeklarationen alten Stils mit Auslassungszeichen jetzt beim Kompilieren mit der \/Za\-Option einen Fehler. Beim Kompilieren mit "\/Ze" wird eine Warnung der Stufe 4 generiert.  Beispiel:  
  
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
  
 Im nächsten Abschnitt [C\-Funktionsdefinitionen](../c-language/c-function-definitions.md) wird die Syntax von Funktionsdefinitionen aufgezeigt, einschließlich des alten Syntaxstils.  Das Nichtterminal für die Parameterliste im alten Syntaxstil ist *identifier\-list*.  
  
## Siehe auch  
 [Übersicht über die Funktionen](../c-language/overview-of-functions.md)