---
title: "Operator delete(CRT)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "delete[]"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "operator delete[]"
  - "vector delete"
ms.assetid: e91bd0df-3815-40ca-950a-67b470518aed
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Operator delete(CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Frees Affinitätsmodells Block zu.  
  
## Syntax  
  
```  
  
      void __cdecl operator delete[](void * object);  
void __cdecl operator delete[](void * object,   
   void * memory) throw();  
void __cdecl operator delete[](void * object,   
   const std::nothrow_t&) throw();  
```  
  
#### Parameter  
 *Arbeitsspeicher*  
 Speicheradresse, die freigegeben wird.  
  
 *Objekt*  
 Ein Zeiger auf das Objekt, das gelöscht wird.  
  
## Hinweise  
 Dieses Format von **Operator löschen** wird als Vektorlöschung, im Gegensatz zu dem Löschungsformular Skalarwert \([Operator](../c-runtime-library/operator-delete-crt.md)\).  
  
 **Operator** `delete[]` gibt den Arbeitsspeicher frei, der von [Operator new&#91;&#93;](../c-runtime-library/new-operator-crt.md) zugeordnet sind.  
  
 Das erste Formular dieses Operators wird als das nonplacement Formular.  Im zweiten und dritten Formulare dieses Operators werden im Allgemeinen nicht vom Code jedoch vorhanden, um dem Compiler eine entsprechende Löschung zu geben, die aufzurufende aufgerufen, wenn eine neue Position fehlschlägt.  
  
 Das erste Formular des Operators wird vom Compiler definiert und nicht new.h erfordert, im Programm eingefügt werden.  
  
 Mit Ausnahme von auslösendem oder NO\-auslösendem Verhalten verhält sich das CRT **Operator**`delete[]` wie [Operator delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md) in der C\+\+\-Standardbibliothek.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`delete[]`|\<new.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Siehe [Operator new&#91;&#93;](../c-runtime-library/new-operator-crt.md) Beispiele zur Verwendung des Operators **löschen**.  
  
## Siehe auch  
 [Speicherbelegung](../c-runtime-library/memory-allocation.md)