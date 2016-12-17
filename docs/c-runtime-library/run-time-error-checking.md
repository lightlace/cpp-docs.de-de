---
title: "Laufzeitfehler&#252;berpr&#252;fung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "c.runtime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Laufzeitfehlerüberprüfung"
  - "Laufzeitfehler, Überprüfen"
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Laufzeitfehler&#252;berpr&#252;fung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die C\-Laufzeitbibliothek enthält die Funktionen, die Laufzeitfehlerüberprüfungen \(RTC\) unterstützen.  Laufzeitfehlerüberprüfung ermöglicht es Ihnen, das Programm zu erstellen, sodass bestimmte Arten Laufzeitfehler gemeldet werden.  Sie geben an, wie die Fehler gemeldet werden und welche Arten von Fehlern ausgegeben werden.  Weitere Informationen finden Sie unter [Laufzeitfehlerüberprüfungen](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md).  
  
 Verwenden Sie die folgenden Funktionen, die Art anpassen, die das Programm Laufzeitfehlerüberprüfung ausführt.  
  
### Laufzeitfehler\-Überprüfungs\-Funktionen  
  
|Funktion|Verwendung|.NET Framework\-Entsprechung|  
|--------------|----------------|----------------------------------|  
|[\_RTC\_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Gibt eine kurze Beschreibung eines Laufzeitfehlerüberprüfungstyps zurück.||  
|[\_RTC\_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Gibt die Gesamtanzahl von Fehlern zurück, die von Laufzeitfehlerüberprüfungen erkannt werden.||  
|[\_RTC\_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Legt eine Funktion als Handler für das Melden von Laufzeitfehlerüberprüfungen fest.||  
|[\_RTC\_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Ordnet einen Fehler zu, der von Laufzeitfehlerüberprüfungen mit einem Typ erkannt wird.||  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)   
 [\/RTC \(Laufzeitfehlerüberprüfungen\)](../build/reference/rtc-run-time-error-checks.md)   
 [runtime\_checks](../preprocessor/runtime-checks.md)   
 [RTC sample](assetId:///b3415b09-f6fd-43dc-8c02-9a910bc2574e)   
 [Debugroutinen](../c-runtime-library/debug-routines.md)