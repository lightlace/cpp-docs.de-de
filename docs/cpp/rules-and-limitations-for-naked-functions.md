---
title: "Regeln und Einschr&#228;nkungen f&#252;r Naked-Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "naked-Funktionen"
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Regeln und Einschr&#228;nkungen f&#252;r Naked-Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Die folgenden Regeln und Einschränkungen treffen auf naked\-Funktionen zu:  
  
-   Die `return`\-Anweisung ist nicht zulässig.  
  
-   Konstrukte für die strukturierte Ausnahmebehandlung und C\+\+\-Ausnahmebehandlung sind nicht zulässig, da sie über den Stapelrahmen entladen werden müssen.  
  
-   Aus demselben Grund ist jede Form von `setjmp` nicht zulässig.  
  
-   Die Verwendung der `_alloca`\-Funktion ist nicht zulässig.  
  
-   Um sicherzustellen, dass kein Initialisierungscode für lokale Variablen vor der Prologsequenz vorkommt, sind initialisierte lokale Variablen im Funktionsbereich nicht zulässig.  Insbesondere ist die Deklaration von C\+\+\-Objekten im Funktionsbereich nicht zulässig.  Es können jedoch initialisierte Daten in einem geschachtelten Bereich vorhanden sein.  
  
-   Framezeigeroptimierung \(die Compileroption "\/Oy"\) wird nicht empfohlen, sie wird jedoch für eine naked\-Funktion automatisch unterdrückt.  
  
-   Sie können C\+\+\-Klassenobjekte nicht im lexikalischen Bereich der Funktion deklarieren.  Sie können jedoch Objekte in einem geschachtelten Block deklarieren.  
  
-   Das `naked`\-Schlüsselwort wird beim Kompilieren mit [\/clr](../build/reference/clr-common-language-runtime-compilation.md) ignoriert.  
  
-   Immer dann, wenn bei mit [\_\_fastcall](../cpp/fastcall.md) aufgerufenen naked\-Funktionen ein Verweis in C\-\/C\+\+\-Code auf eines der Registerargumente vorhanden ist, sollte der Prologcode die Werte dieses Registers in den Stapelspeicherort für diese Variable speichern.  Beispiel:  
  
```  
// nkdfastcl.cpp  
// compile with: /c  
// processor: x86  
__declspec(naked) int __fastcall  power(int i, int j) {  
   // calculates i^j, assumes that j >= 0  
  
   // prolog  
   __asm {  
      push ebp  
      mov ebp, esp  
      sub esp, __LOCAL_SIZE  
     // store ECX and EDX into stack locations allocated for i and j  
     mov i, ecx  
     mov j, edx  
   }  
  
   {  
      int k = 1;   // return value  
      while (j-- > 0)   
         k *= i;  
      __asm {   
         mov eax, k   
      };  
   }  
  
   // epilog  
   __asm {  
      mov esp, ebp  
      pop ebp  
      ret  
   }  
}  
```  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Naked\-Funktionsaufrufe](../cpp/naked-function-calls.md)