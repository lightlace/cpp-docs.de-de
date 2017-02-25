---
title: "runtime_checks | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.runtime_checks"
  - "runtime_checks_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "runtime_checks-Pragma"
  - "Pragmas, runtime_checks"
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# runtime_checks
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dient der Deaktivierung oder Wiederherstellung der [\/RTC](../build/reference/rtc-run-time-error-checks.md)\-Einstellungen.  
  
## Syntax  
  
```  
  
#pragma runtime_checks(  
"[runtime_checks]", {restore | off} )  
```  
  
## Hinweise  
 Sie können nur Laufzeitüberprüfungen aktivieren, die mit einer Compileroption aktiviert wurden. Wenn Sie beispielsweise keine \/RTCs angeben, ermöglicht die Angabe von `#pragma runtime_checks( "s", restore)` keine Überprüfung der Stapelrahmen.  
  
 Das **runtime\_checks**\-Pragma muss außerhalb der Funktion angezeigt werden und tritt für die erste definierte Funktion in Kraft, nachdem das Pragma sichtbar ist. Die Argumente **restore** und **off** schalten die in *runtime\_checks* angegebenen Optionen ein oder aus.  
  
 Die Option *runtime\_checks* kann leer sein oder mehrere Parameter aus der folgenden Tabelle enthalten.  
  
### Parameter des runtime\_checks\-Pragmas  
  
|Parameter|Typ der Laufzeitüberprüfung|  
|---------------|---------------------------------|  
|**s**|Aktiviert die Überprüfung des Stapels \(Frames\).|  
|**c**|Meldet die Zuweisung eines Werts zu einem kleineren Datentyp, der zu einem Datenverlust führt.|  
|**n**|Zeigt an, wenn eine Variable verwendet wird, bevor sie definiert ist.|  
  
 Hierbei handelt es sich um dieselben Buchstaben, die mit der \/RTC\-Compileroption verwendet werden. Zum Beispiel:  
  
```  
#pragma runtime_checks( "sc", restore )  
```  
  
 Verwenden des **runtime\_checks**\-Pragmas mit einer leeren Zeichenfolge \(**""**\) ist eine besondere Form der Direktive:  
  
-   Wenn Sie den Parameter **off** verwenden, werden die in der vorstehenden Tabelle aufgeführten Laufzeitfehlerüberprüfungen deaktiviert.  
  
-   Wenn Sie den **restore**\-Parameter verwenden, werden die Laufzeitfehlerüberprüfungen auf die mit der \/RTC\-Compileroption angegebenen zurückgesetzt.  
  
```  
#pragma runtime_checks( "", off )  
.  
.  
.  
#pragma runtime_checks( "", restore )   
```  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [RTC sample](assetId:///b3415b09-f6fd-43dc-8c02-9a910bc2574e)