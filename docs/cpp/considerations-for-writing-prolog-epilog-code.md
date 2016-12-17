---
title: "&#220;berlegungen zum Schreiben von Prolog- und Epilogcode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__LOCAL_SIZE-Konstante"
  - "Epilogcode"
  - "Prologcode"
  - "Stapelrahmenlayout"
  - "Stapel, Stapelrahmenlayout"
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;berlegungen zum Schreiben von Prolog- und Epilogcode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Vor dem Schreiben eigener Prolog\- und Epilogcodesequenzen ist es wichtig, zu verstehen, wie der Stapelrahmen festgelegt ist.  Es ist auch hilfreich zu wissen, wie das **\_\_LOCAL\_SIZE**\-Symbol verwendet werden kann.  
  
##  <a name="_pluslang_c.2b2b_.stack_frame_layout"></a> Stapelrahmenlayout  
 In diesem Beispiel wird der Standardprologcode veranschaulicht, der in einer 32\-Bit\-Funktion enthalten sein kann:  
  
```  
push        ebp                ; Save ebp  
mov         ebp, esp           ; Set stack frame pointer  
sub         esp, localbytes    ; Allocate space for locals  
push        <registers>        ; Save registers  
```  
  
 Die `localbytes`\-Variable gibt die Anzahl von Bytes an, die auf dem Stapel für lokale Variablen erforderlich sind. Die `<registers>`\-Variable ist ein Platzhalter, der die Liste der Register darstellt, die auf dem Stapel gespeichert werden sollen.  Nach dem Verschieben der Register können Sie alle weiteren entsprechenden Daten auf dem Stapel platzieren.  Im Folgenden wird der entsprechende Epilogcode dargestellt:  
  
```  
pop         <registers>   ; Restore registers  
mov         esp, ebp      ; Restore stack pointer  
pop         ebp           ; Restore ebp  
ret                       ; Return from function  
```  
  
 Der Stapel wächst immer nach unten \(von hohen zu niedrigen Speicheradressen\).  Der Basiszeiger \(`ebp`\) zeigt auf den abgelegten `ebp`\-Wert.  Der Gültigkeitsbereich der lokalen Variablen beginnt bei `ebp-4`.  Um auf lokale Variablen zuzugreifen, berechnen Sie einen Offset von `ebp`, indem Sie den entsprechenden Wert von `ebp` subtrahieren.  
  
##  <a name="_pluslang___local_size"></a> \_\_LOCAL\_SIZE  
 Der Compiler stellt das Symbol **\_\_LOCAL\_SIZE** für die Verwendung im Inlineassemblerblock des Funktionsprologcodes bereit.  Mit diesem Symbol wird Speicherplatz für lokale Variablen im Stapelrahmen im benutzerdefinierten Prologcode zugeordnet.  
  
 Der Compiler bestimmt den Wert von **\_\_LOCAL\_SIZE**.  Sein Wert ist die Gesamtzahl von Bytes aller benutzerdefinierten lokalen Variablen und der vom Compiler generierten temporären Variablen.  **\_\_LOCAL\_SIZE** kann nur als unmittelbarer Operand verwendet werden. Er kann nicht in einem Ausdruck verwendet werden.  Sie dürfen den Wert dieses Symbols nicht ändern oder neu definieren.  Beispiel:  
  
```  
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov        eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 Im folgenden Beispiel für eine naked\-Funktion, die benutzerdefinierte Prolog\- und Epilogsequenzen enthält, wird das **\_\_LOCAL\_SIZE**\-Symbol in der Prologsequenz verwendet:  
  
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
  
### END Microsoft\-spezifisch  
  
## Siehe auch  
 [Naked\-Funktionsaufrufe](../cpp/naked-function-calls.md)