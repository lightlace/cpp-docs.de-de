---
title: "&#220;berlegungen zum Schreiben von Prolog- und Epilogcode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__LOCAL_SIZE-Konstante"
  - "Layouts, Stapelrahmen"
  - "Stapelrahmenlayout"
  - "Stapel, Stapelrahmenlayout"
ms.assetid: 3b8addec-e809-48e4-b1d0-5bad133bd4b8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# &#220;berlegungen zum Schreiben von Prolog- und Epilogcode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Vor dem Schreiben eigener Prolog\- und Epilogcodesequenzen ist es wichtig, zu verstehen, wie der Stapelrahmen festgelegt ist.  Es ist auch hilfreich zu wissen, wie die vordefinierte **\_\_LOCAL\_SIZE**\-Konstante verwendet werden kann.  
  
##  <a name="_clang_c_stack_frame_layout"></a> Stapelrahmenlayout bei C  
 In diesem Beispiel wird der Standardprologcode veranschaulicht, der in einer 32\-Bit\-Funktion enthalten sein kann:  
  
```  
push     ebp                 ; Save ebp  
mov      ebp, esp            ; Set stack frame pointer  
sub      esp, localbytes     ; Allocate space for locals  
push     <registers>         ; Save registers  
```  
  
 Die `localbytes`\-Variable gibt die Anzahl von Bytes an, die auf dem Stapel für lokale Variablen erforderlich sind. Die `registers`\-Variable ist ein Platzhalter, der die Liste der Register darstellt, die auf dem Stapel gespeichert werden sollen.  Nach dem Verschieben der Register können Sie alle weiteren entsprechenden Daten auf dem Stapel platzieren.  Im Folgenden wird der entsprechende Epilogcode dargestellt:  
  
```  
pop      <registers>         ; Restore registers  
mov      esp, ebp            ; Restore stack pointer  
pop      ebp                 ; Restore ebp  
ret                          ; Return from function  
```  
  
 Der Stapel wächst immer nach unten \(von hohen zu niedrigen Speicheradressen\).  Der Basiszeiger \(`ebp`\) zeigt auf den abgelegten `ebp`\-Wert.  Der Gültigkeitsbereich der lokalen Variablen beginnt bei `ebp-2`.  Um auf lokale Variablen zuzugreifen, berechnen Sie einen Offset von `ebp`, indem Sie den entsprechenden Wert von `ebp` subtrahieren.  
  
##  <a name="_clang_the___local_size_constant"></a> Die \_\_LOCAL\_SIZE\-Konstante  
 Der Compiler stellt eine Konstante, **\_\_LOCAL\_SIZE**, für die Verwendung im Inlineassemblerblock des Funktionsprologcodes bereit.  Mit dieser Konstanten wird Speicherplatz für lokale Variablen im Stapelrahmen im benutzerdefinierten Prologcode zugeordnet.  
  
 Der Compiler bestimmt den Wert von **\_\_LOCAL\_SIZE**.  Der Wert ist die Gesamtzahl von Bytes aller benutzerdefinierten lokalen Variablen und der vom Compiler generierten temporären Variablen.  **\_\_LOCAL\_SIZE** kann nur als unmittelbarer Operand verwendet werden. Er kann nicht in einem Ausdruck verwendet werden.  Sie dürfen den Wert dieser Konstanten nicht ändern oder neu definieren.  Beispiel:  
  
```  
mov      eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov      eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 Das folgende Beispiel einer bloßen Funktion, welche benutzerdefinierte Prolog\- und Epilogsequenzen enthält, verwendet **\_\_LOCAL\_SIZE** in der Prologsequenz:  
  
```  
__declspec ( naked ) func()  
{  
   int i;  
   int j;  
  
   __asm      /* prolog */  
      {  
      push   ebp  
      mov      ebp, esp  
      sub      esp, __LOCAL_SIZE  
      }  
  
   /* Function body */  
  
   __asm      /* epilog */  
      {  
      mov      esp, ebp  
      pop      ebp  
      ret  
      }  
}     
```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Naked\-Funktionen](../c-language/naked-functions.md)