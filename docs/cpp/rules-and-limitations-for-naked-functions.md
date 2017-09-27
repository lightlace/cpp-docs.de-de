---
title: "Regeln und Einschränkungen für Naked-Funktionen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- naked functions
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a02eb245ffae169f75f5d8edb261d0af9618856d
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="rules-and-limitations-for-naked-functions"></a>Regeln und Einschränkungen für Naked-Funktionen
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Die folgenden Regeln und Einschränkungen treffen auf naked-Funktionen zu:  
  
-   Die `return`-Anweisung ist nicht zulässig.  
  
-   Konstrukte für die strukturierte Ausnahmebehandlung und C++-Ausnahmebehandlung sind nicht zulässig, da sie über den Stapelrahmen entladen werden müssen.  
  
-   Aus demselben Grund ist jede Form von `setjmp` nicht zulässig.  
  
-   Die Verwendung der `_alloca`-Funktion ist nicht zulässig.  
  
-   Um sicherzustellen, dass kein Initialisierungscode für lokale Variablen vor der Prologsequenz vorkommt, sind initialisierte lokale Variablen im Funktionsbereich nicht zulässig. Insbesondere ist die Deklaration von C++-Objekten im Funktionsbereich nicht zulässig. Es können jedoch initialisierte Daten in einem geschachtelten Bereich vorhanden sein.  
  
-   Framezeigeroptimierung (die Compileroption "/Oy") wird nicht empfohlen, sie wird jedoch für eine naked-Funktion automatisch unterdrückt.  
  
-   Sie können C++-Klassenobjekte nicht im lexikalischen Bereich der Funktion deklarieren. Sie können jedoch Objekte in einem geschachtelten Block deklarieren.  
  
-   Die `naked` Schlüsselwort wird ignoriert, bei der Kompilierung mit ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md).  
  
-   Für [__fastcall](../cpp/fastcall.md) naked-Funktionen, wenn ein Verweis in C-/C++-Code auf eines der Registerargumente vorhanden ist, sollte der Prologcode die Werte dieses Registers in den Stapelspeicherort für diese Variable speichern. Zum Beispiel:  
  
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
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Naked-Funktionsaufrufe](../cpp/naked-function-calls.md)
