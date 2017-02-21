---
title: "Verwenden und Beibehalten von Registern in der Inlineassembly | Microsoft Docs"
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
  - "__asm-Schlüsselwort [C++], Registerwerte"
  - "Inlineassembly, Register"
  - "Beibehalten von Registern"
  - "Register, Inlineassembly"
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Verwenden und Beibehalten von Registern in der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Im Allgemeinen sollten Sie nicht davon ausgehen, dass ein Register über einen angegebenen Wert verfügt, wenn ein `__asm`\-Block beginnt.  Registerwerte nicht garantiert werden, über separate `__asm` Blöcke beibehalten werden muss.  Wenn Sie einen Block von Inlinecodes beenden und andere beginnen, können Sie nicht auf die Register im zweiten Block verlassen, um ihre Werte aus dem ersten Block festzulegen.  Ein `__asm`\-Block erbt, welche Registerwerte in normalen Programmablauf resultieren.  
  
 Wenn Sie die `__fastcall` \- Aufrufkonvention verwenden, führt der Compiler Funktionsargumente in Registern statt auf des Stapels.  Dies kann Probleme mit Funktionen `__asm` Blöcke erstellen, da keine Möglichkeit hat, eine Funktion zu übermitteln, welcher Parameter ist in der Register.  Wenn die Funktion einen Fall EAX Parameter in sofort zu empfangen und etwas Anderes an EAX speichert, ist der erste Parameter verloren.  Außerdem müssen Sie im ECX\-Register in jeder Funktion beibehalten, die mit `__fastcall`deklariert ist.  
  
 Um solche Register Konflikte zu vermeiden, verwenden Sie nicht die `__fastcall` Konvention für Funktionen die einen `__asm`\-Block enthalten.  Wenn Sie die Konvention `__fastcall` global mit der Compileroption \/Gr\- angeben, deklarieren Sie alle Funktionen, die einen `__asm`\-Block mit `__cdecl` oder `__stdcall`enthält.  \(Das `__cdecl`\-Attribut weist den Compiler an, um die C\-Aufrufkonvention für diese Funktion zu verwenden.\) Wenn Sie nicht mit \/Gr kompilieren, sollten Sie die Funktion mit dem `__fastcall`\-Attribut zu deklarieren.  
  
 Wenn funktioniert die Verwendung von `__asm` , um Assemblersprache in C\/C\+\+ geschrieben werden soll, muss keine Sie die EAX\-, EBX\-, ECX\-, EDX\-, ESI\- oder EDI\-Register beizubehalten.  Beispielsweise wird im POWER2.C\-Beispiel in [Schreiben\-Funktionen mit Inlineassembly](../../assembler/inline/writing-functions-with-inline-assembly.md), behält die `power2`\-Funktion nicht den Wert im EAX\-Register bei.  Die Verwendung dieser Register auswirken, da die Qualität des Codes für diese Register nicht verwendet werden kann, um Werte zu `__asm` Blöcke zu speichern.  Darüber hinaus indem Sie EBX, oder ESI EDI im Inlineassemblycode verwenden, Erzwingen von der Compiler diese Register in der Funktion einleitung und Epilog zu speichern und wiederherstellen.  
  
 Sie können andere Register, die Sie beibehalten werden \(z DS, kennzeichnet ss, SP, BP\) für Register und den Bereich des `__asm`\-Blocks verwenden.  Sie sollten die ESP\- EBP\-Register und beibehalten, es sei denn, Sie einige Grund sie zu ändern \(Stapel wechseln, z\).  Siehe auch [Optimieren der Inlineassembly](../../assembler/inline/optimizing-inline-assembly.md).  
  
 Eine SSE\-Typen erfordern die Acht BYTE\-Stapel erzwingen und die Ausrichtung der Compiler dynamischen Stapel Ausrichtung Code auszugeben.  Um die lokalen Variablen und Funktionsparameter nach der Ausrichtung zuzugreifen, wartet der Compiler zwei Framezeiger.  Wenn der Compiler auslassung Framezeiger \(FPO\) ausführt, verwendet er EBP und ESP.  Wenn der Compiler keine FPO ausführt, verwendet er EBX und EBP.  Um Code wird ordnungsgemäß zu gewährleisten, ändern Sie nicht EBX in asm\-Code wenn die Funktion dynamische Stapel benötigt die Ausrichtung der Framezeiger ändern könnte.  Entweder verschieben Sie die Acht BYTE ausgerichteten Typen aus der Funktion oder vermeiden Sie mithilfe EBX.  
  
> [!NOTE]
>  Wenn der Inlineassemblycode das Richtungs flag mithilfe der std\- oder CLD\-Anweisungen ändert, müssen Sie das Flag auf den ursprünglichen Wert zurücksetzen.  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)