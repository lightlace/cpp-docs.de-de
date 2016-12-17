---
title: "Argumentzugriff"
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
  - "c.arguments"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Argumentzugriffsmakros [C++]"
  - "Argumentlisten variabler Länge"
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Argumentzugriff
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`va_arg`, `va_end` und `va_start`\-Makros ermöglichen den Zugriff auf den Funktionsargumenten, wenn die Anzahl der Argumente variabel ist.  Diese Makros werden in STDARG.H bei ANSI C\-Kompatibilität und in VARARGS.H für Kompatibilität mit UNIX\-System V. definiert.  
  
### Argument\-Zugriffs\-Makros  
  
|Makro|Verwendung|.NET Framework\-Entsprechung|  
|-----------|----------------|----------------------------------|  
|[va\_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Rufen Sie Argument aus der Liste ab|[\<caps:sentence id\="tgt9" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>System::ParamArrayAttribute Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
|[va\_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Rücksetzungszeiger|[\<caps:sentence id\="tgt12" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>System::ParamArrayAttribute Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
|[va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Legen Sie Zeiger auf dem Starten der Argumentliste fest|[\<caps:sentence id\="tgt15" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>System::ParamArrayAttribute Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)