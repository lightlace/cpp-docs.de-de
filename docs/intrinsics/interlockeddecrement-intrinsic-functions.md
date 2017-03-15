---
title: "Systeminterne Funktionen „_InterlockedDecrement“ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedDecrement16_rel_cpp"
  - "_InterlockedDecrement16_acq_cpp"
  - "_InterlockedDecrement16_rel"
  - "_InterlockedDecrement64_acq"
  - "_InterlockedDecrement_nf"
  - "_InterlockedDecrement16_nf"
  - "_InterlockedDecrement64_rel_cpp"
  - "_InterlockedDecrement_rel_cpp"
  - "_InterlockedDecrement16_acq"
  - "_InterlockedDecrement64_acq_cpp"
  - "_InterlockedDecrement_rel"
  - "_InterlockedDecrement64_nf"
  - "_InterlockedDecrement16_cpp"
  - "_InterlockedDecrement64"
  - "_InterlockedDecrement_cpp"
  - "_InterlockedDecrement64_rel"
  - "_InterlockedDecrement16"
  - "_InterlockedDecrement"
  - "_InterlockedDecrement64_cpp"
  - "_InterlockedDecrement_acq"
  - "_InterlockedDecrement_acq_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systeminterne Funktion „_InterlockedDecrement“"
  - "Systeminterne Funktion „_InterlockedDecrement_acq“"
  - "Systeminterne Funktion „_InterlockedDecrement_nf“"
  - "Systeminterne Funktion „_InterlockedDecrement_rel“"
  - "Systeminterne Funktion „_InterlockedDecrement16“"
  - "Systeminterne Funktion „_InterlockedDecrement16_acq“"
  - "Systeminterne Funktion „_InterlockedDecrement16_nf“"
  - "Systeminterne Funktion „_InterlockedDecrement16_rel“"
  - "Systeminterne Funktion „_InterlockedDecrement64“"
  - "Systeminterne Funktion „_InterlockedDecrement64_acq“"
  - "Systeminterne Funktion „_InterlockedDecrement64_nf“"
  - "Systeminterne Funktion „_InterlockedDecrement64_rel“"
  - "Systeminterne Funktion „InterlockedDecrement“"
  - "Systeminterne Funktion „InterlockedDecrement_acq“"
  - "Systeminterne Funktion „InterlockedDecrement_rel“"
  - "Systeminterne Funktion „InterlockedDecrement16“"
  - "Systeminterne Funktion „InterlockedDecrement64“"
  - "Systeminterne Funktion „InterlockedDecrement64_acq“"
  - "Systeminterne Funktion „InterlockedDecrement64_rel“"
ms.assetid: 5268fce3-86b5-4b2b-b96c-2e531a3fb9b5
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# Systeminterne Funktionen „_InterlockedDecrement“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Stellt systeminterne Compiler\-Unterstützung für die Win32\-[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] [InterlockedDecrement](http://msdn.microsoft.com/library/ms683580.aspx)\-Funktion bereit.  
  
## Syntax  
  
```  
long _InterlockedDecrement(  
   long * lpAddend  
);  
long _InterlockedDecrement_acq(  
   long * lpAddend  
);  
long _InterlockedDecrement_rel(  
   long * lpAddend  
);  
long _InterlockedDecrement_nf(  
   long * lpAddend  
);  
short _InterlockedDecrement16(  
   short * lpAddend  
);  
short _InterlockedDecrement16_acq(  
   short * lpAddend  
);  
short _InterlockedDecrement16_rel(  
   short * lpAddend  
);  
short _InterlockedDecrement16_nf(  
   short * lpAddend  
);  
__int64 _InterlockedDecrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedDecrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedDecrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedDecrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### Parameter  
 \[in, out\] `lpAddend`  
 Zeiger auf die zu verringernde Variable.  
  
## Rückgabewert  
 Der Rückgabewert ist der resultierende verringerte Wert.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`_InterlockedDecrement`, `_InterlockedDecrement16`, `_InterlockedDecrement64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_InterlockedDecrement_acq`, `_InterlockedDecrement_rel`, `_InterlockedDecrement_nf`, `_InterlockedDecrement16_acq`, `_InterlockedDecrement16_rel`, `_InterlockedDecrement16_nf`, `_InterlockedDecrement64_acq`, `_InterlockedDecrement64_rel`, `_InterlockedDecrement64_nf`,|ARM|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Es gibt mehrere Varianten von `_InterlockedDecrement`, die sich basierend auf den beinhalteten Datentypen und in Abhängigkeit davon unterscheiden, ob prozessorspezifische Semantiken zum Abrufen bzw. Freigeben verwendet werden.  
  
 Während die `_InterlockedDecrement`\-Funktion mit 32\-Bit\-Ganzzahlwerten arbeitet, verwendet `_InterlockedDecrement16`16\-Bit\-Ganzzahlwerte und `_InterlockedDecrement64` 64\-Bit\-Ganzzahlwerte.  
  
 Verwenden Sie auf ARM\-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel`, wenn Sie Semantiken abrufen und freigeben müssen, beispielsweise am Anfang und Ende eines kritischen Abschnitts.  Die systeminternen Funktionen mit einer `_nf`\-Suffix \("no fence"\) fungieren nicht als Speicherbarriere.  
  
 Die Variable, auf die der `lpAddend`\-Parameter zeigt, muss an einer 32\-Bit\-Grenze ausgerichtet sein; andernfalls schlägt diese Funktion auf x86\-Multiprozessorsystemen und allen Nicht\-x86\-Systemen fehl.  Weitere Informationen finden Sie unter [ausrichten](../cpp/align-cpp.md).  
  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## Beispiel  
  
```  
// compiler_intrinsics_interlocked.cpp  
// compile with: /Oi  
#define _CRT_RAND_S  
  
#include <cstdlib>  
#include <cstdio>  
#include <process.h>  
#include <windows.h>  
  
// To declare an interlocked function for use as an intrinsic,  
// include intrin.h and put the function in a #pragma intrinsic   
// statement.  
#include <intrin.h>  
  
#pragma intrinsic (_InterlockedIncrement)  
  
// Data to protect with the interlocked functions.  
volatile LONG data = 1;  
  
void __cdecl SimpleThread(void* pParam);  
  
const int THREAD_COUNT = 6;  
  
int main() {  
   DWORD num;  
   HANDLE threads[THREAD_COUNT];  
   int args[THREAD_COUNT];  
   int i;  
  
   for (i = 0; i < THREAD_COUNT; i++) {  
     args[i] = i + 1;  
     threads[i] = reinterpret_cast<HANDLE>(_beginthread(SimpleThread, 0,   
                           args + i));  
      if (threads[i] == reinterpret_cast<HANDLE>(-1))  
         // error creating threads  
         break;  
   }  
  
   WaitForMultipleObjects(i, threads, true, INFINITE);  
}  
  
// Code for our simple thread  
void __cdecl SimpleThread(void* pParam) {  
   int threadNum = *((int*)pParam);  
   int counter;  
   unsigned int randomValue;  
   unsigned int time;  
   errno_t err = rand_s(&randomValue);  
  
   if (err == 0) {  
      time = (unsigned int) ((double) randomValue / (double) UINT_MAX * 500);  
      while (data < 100) {  
         if (data < 100) {  
            _InterlockedIncrement(&data);  
            printf_s("Thread %d: %d\n", threadNum, data);  
         }  
  
         Sleep(time);   // wait up to half of a second  
      }  
   }  
  
   printf_s("Thread %d complete: %d\n", threadNum, data);  
}  
```  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Konflikt mit dem x86\-Compiler](../build/conflicts-with-the-x86-compiler.md)