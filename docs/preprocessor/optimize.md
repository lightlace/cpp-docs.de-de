---
title: "optimize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.optimize"
  - "optimize_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "optimize-Pragma"
  - "Pragmas, optimize"
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# optimize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Optimierungen an, die für jede einzelne Funktion durchgeführt werden sollen.  
  
## Syntax  
  
```  
  
#pragma optimize( "[optimization-list]", {on | off} )  
```  
  
## Hinweise  
 Das **optimize**\-Pragma muss außerhalb der Funktion angezeigt werden und tritt mit der ersten Funktionsdefinition in Kraft, nachdem das Pragma angezeigt wird.  Mit den **on**\- und **off**\-Argumenten werden Optionen aktiviert oder deaktiviert, die in der *Optimierungsliste* festgelegt sind.  
  
 Die *Optimierungsliste* kann keine oder mehrere Parameter aus der folgenden Tabelle enthalten.  
  
### Parameter des optimize\-Pragmas  
  
|Parameter|Typ der Optimierung|  
|---------------|-------------------------|  
|**g**|Aktivieren globale Optimierungen.|  
|**s** oder **t**|Geben kurze oder schnelle Sequenzen von Computercode an.|  
|**y**|Generieren Framezeiger im Programmstapel.|  
  
 Hierbei handelt es sich um dieselben Buchstaben, die mit den [\/O](../build/reference/o-options-optimize-code.md)\-Compileroptionen verwendet werden.  Beispielsweise ist folgendes Pragma mit der **\/Os**\-Compileroption identisch:  
  
```  
#pragma optimize( "ts", on )  
```  
  
 Die Verwendung des **optimize**\-Pragmas mit der leeren Zeichenfolge \(**""**\) ist eine besondere Form der Direktive:  
  
 Wenn Sie den **off**\-Parameter verwenden, werden die in der Tabelle weiter oben in diesem Thema angegebenen Optimierungen deaktiviert.  
  
 Wenn Sie den **on**\-Parameter verwenden, werden die Optimierungen auf die Optimierungen zurückgesetzt, die Sie mit der [\/O](../build/reference/o-options-optimize-code.md)\-Compileroption angegeben haben.  
  
```  
#pragma optimize( "", off )  
.  
.  
.  
#pragma optimize( "", on )   
```  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)