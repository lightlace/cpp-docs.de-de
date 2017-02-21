---
title: "operator delete (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator delete"
  - "scalar delete"
ms.assetid: bcd0066a-0022-45f5-af4c-9007c64a6b89
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# operator delete (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Frees Affinitätsmodells Block zu.  
  
## Syntax  
  
```  
  
      void __cdecl operator delete(  
   void * object  
);  
void __cdecl operator delete(  
   void * object,   
   void * memory  
) throw();  
void __cdecl operator delete(  
   void * object,   
   const std::nothrow_t&  
) throw();  
```  
  
#### Parameter  
 *Arbeitsspeicher*  
 Speicheradresse, die freigegeben wird.  
  
 *Objekt*  
 Ein Zeiger auf das Objekt, das gelöscht wird.  
  
## Hinweise  
 Dieses Format von **Operator löschen** wird als Skalare Lösch\-, im Gegensatz zum Vektorlöschungsformular \([Operator delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)\).  
  
 **Operator löschen** gibt den Arbeitsspeicher frei, der von [Operator neu](../c-runtime-library/operator-new-crt.md) zugeordnet sind.  
  
 Das erste Formular dieses Operators wird als das nonplacement Formular.  Im zweiten und dritten Formulare dieses Operators werden im Allgemeinen nicht vom Code jedoch vorhanden, um dem Compiler eine entsprechende Löschung zu geben, die aufzurufende aufgerufen, wenn eine neue Position fehlschlägt.  
  
 Das erste Formular des Operators wird vom Compiler definiert und nicht new.h erfordert, im Programm eingefügt werden.  
  
 Mit Ausnahme von auslösendem oder NO\-auslösendem Verhalten verhält sich das CRT **Operatorlöschen** wie [Operator](../Topic/operator%20delete%20\(%3Cnew%3E\).md) in der C\+\+\-Standardbibliothek.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|**delete**|\<new.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Siehe [Operator neu](../c-runtime-library/operator-new-crt.md) Beispiele zur Verwendung des Operators **löschen**.  
  
## Siehe auch  
 [Speicherbelegung](../c-runtime-library/memory-allocation.md)