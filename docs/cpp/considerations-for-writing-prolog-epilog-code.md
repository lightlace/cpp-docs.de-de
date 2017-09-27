---
title: "Überlegungen zum Schreiben von Code Prolog-Epilog | Microsoft Docs"
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
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
caps.latest.revision: 8
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
ms.openlocfilehash: 4dc75755fafb569c06dcb41b77ff54ebc0403b2d
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="considerations-for-writing-prologepilog-code"></a>Überlegungen für das Schreiben des Prolog-/Epilogcodes
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Vor dem Schreiben eigener Prolog- und Epilogcodesequenzen ist es wichtig, zu verstehen, wie der Stapelrahmen festgelegt ist. Es ist auch hilfreich zu wissen, wie Sie die **__LOCAL_SIZE** Symbol.  
  
##  <a name="_pluslang_c.2b2b_.stack_frame_layout"></a>Stapelrahmenlayout  
 In diesem Beispiel wird der Standardprologcode veranschaulicht, der in einer 32-Bit-Funktion enthalten sein kann:  
  
```  
push        ebp                ; Save ebp  
mov         ebp, esp           ; Set stack frame pointer  
sub         esp, localbytes    ; Allocate space for locals  
push        <registers>        ; Save registers  
```  
  
 Die `localbytes`-Variable gibt die Anzahl von Bytes an, die auf dem Stapel für lokale Variablen erforderlich sind. Die `<registers>`-Variable ist ein Platzhalter, der die Liste der Register darstellt, die auf dem Stapel gespeichert werden sollen. Nach dem Verschieben der Register können Sie alle weiteren entsprechenden Daten auf dem Stapel platzieren. Im Folgenden wird der entsprechende Epilogcode dargestellt:  
  
```  
pop         <registers>   ; Restore registers  
mov         esp, ebp      ; Restore stack pointer  
pop         ebp           ; Restore ebp  
ret                       ; Return from function  
```  
  
 Der Stapel wächst immer nach unten (von hohen zu niedrigen Speicheradressen). Der Basiszeiger (`ebp`) zeigt auf den abgelegten `ebp`-Wert. Der Gültigkeitsbereich der lokalen Variablen beginnt bei `ebp-4`. Um auf lokale Variablen zuzugreifen, berechnen Sie einen Offset von `ebp`, indem Sie den entsprechenden Wert von `ebp` subtrahieren.  
  
##  <a name="_pluslang___local_size"></a>__LOCAL_SIZE  
 Der Compiler stellt ein Symbol **__LOCAL_SIZE**, für die Verwendung im inlineassemblerblock des funktionsprologcodes. Mit diesem Symbol wird Speicherplatz für lokale Variablen im Stapelrahmen im benutzerdefinierten Prologcode zugeordnet.  
  
 Der Compiler bestimmt den Wert von **__LOCAL_SIZE**. Sein Wert ist die Gesamtzahl von Bytes aller benutzerdefinierten lokalen Variablen und der vom Compiler generierten temporären Variablen. **__LOCAL_SIZE** kann nur als unmittelbarer Operand verwendet werden. Er kann nicht in einem Ausdruck verwendet werden. Sie dürfen den Wert dieses Symbols nicht ändern oder neu definieren. Zum Beispiel:  
  
```  
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov        eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 Im folgende Beispiel einer bloßen Funktion, die benutzerdefinierte Prolog- und epilogsequenzen enthält Sequenzen verwendet die **__LOCAL_SIZE** Symbol in der prologsequenz:  
  
```  
// the__local_size_symbol.cpp  
// processor: x86  
__declspec ( naked ) int main() {  
   int i;  
   int j;  
  
   __asm {      /* prolog */  
      push   ebp  
      mov      ebp, esp  
      sub      esp, __LOCAL_SIZE  
      }  
  
   /* Function body */  
   __asm {   /* epilog */  
      mov      esp, ebp  
      pop      ebp  
      ret  
      }  
}  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Naked-Funktionsaufrufe](../cpp/naked-function-calls.md)
