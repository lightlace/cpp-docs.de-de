---
title: "Compilerfehler C2268"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2268"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2268"
ms.assetid: 0ed055c9-3c6f-4df2-a5b6-85cf0e01a249
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2268
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Funktion" ist eine vom Compiler vordefinierte Bibliothekhilfsfunktion. Bibliothekhilfsfunktionen werden mit "\/GL" nicht unterstützt. Kompilieren Sie die Objektdatei "Datei" ohne "\/GL".  
  
 Eine im Quellcode definierte Funktion hat den gleichen Namen wie eine interne Compilerfunktion. Kompilieren Sie das Modul mit der Funktion ohne [\/GL](../../build/reference/gl-whole-program-optimization.md).  
  
 Im folgenden Beispiel wird C2268 generiert:  
  
```  
// C2268.c // compile with: /c // processor: x86 extern int SHFusionLoadLibrary(int lpLibFileName); int __cdecl _except_handler3(void) { return SHFusionLoadLibrary(0); } extern int main(void); void* mainCRTStartup(void* p) { p = main; return p; }  
```  
  
 und anschließend:  
  
```  
// C2268b.c // compile with: C2268.c /EHsc /GL /Ob0 /O2 /Fa /GS- /link /nodefaultlib // processor: x86 extern int SHFusionLoadLibrary(int lpLibFileName); extern int __cdecl _except_handler3(void); extern void mainCRTStartup(void*); int g = 2; #define ENTERCONTEXT(fail) \ int ulCookie = 0;\ if (!SHActivateContext(&ulCookie)) \ return fail;\ __try { #define LEAVECONTEXT \ } __finally {SHDeactivateContext(ulCookie);} int SHActivateContext(int* a) { return *a == g || !*a ||_except_handler3(); } void SHDeactivateContext(int a) { g = a; } int SHFusionLoadLibrary(int lpLibFileName) {   // C2268 ENTERCONTEXT(0) g = lpLibFileName; LEAVECONTEXT return lpLibFileName; } int main(void) { g = SHFusionLoadLibrary(10); return 0; }  
```