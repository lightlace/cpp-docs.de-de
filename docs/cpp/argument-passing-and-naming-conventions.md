---
title: "Argument&#252;bergabe und Benennungskonventionen"
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
  - "Argumentübergabe [C++], Konventionen"
  - "Argumente [C++], Benennen"
  - "Argumente [C++], Übergeben"
  - "Argumente [C++], Erweitern"
  - "Codekonventionen, Argumente"
  - "Konventionen [C++], Argumentnamen"
  - "Benennungskonventionen [C++], Argumente"
  - "Übergeben von Argumenten, Konventionen"
  - "Register, Rückgabewerte"
  - "thiscall-Schlüsselwort [C++]"
ms.assetid: de468979-eab8-4158-90c5-c198932f93b9
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Argument&#252;bergabe und Benennungskonventionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Mithilfe der Visual C\+\+\-Compiler können Sie Konventionen zum Übergeben von Argumenten und Zurückgeben von Werten zwischen Funktionen und Aufrufern festlegen.  Nicht alle Konventionen sind auf allen unterstützten Plattformen verfügbar, und einige Konventionen verwenden plattformspezifische Implementierungen.  In den meisten Fällen werden Schlüsselwörter oder Compilerschalter, die eine nicht unterstützte Konvention auf einer bestimmten Plattform angeben, ignoriert und die Plattformstandardkonvention wird verwendet.  
  
 Auf x86\-Plattformen werden alle Argumente bei Übergabe auf 32 Bits erweitert.  Rückgabewerte werden ebenfalls auf 32 Bit erweitert und im EAX\-Register zurückgegeben. Eine Ausnahme bilden 8\-Byte\-Strukturen, die im EDX:EAX\-Registerpaar zurückgegeben werden.  Größere Strukturen werden im EAX\-Register als Zeiger auf ausgeblendete Rückgabestrukturen zurückgegeben.  Parameter werden auf von rechts nach links auf den Stapel verschoben.  Strukturen, die keine PODs sind, werden nicht in Registern zurückgegeben.  
  
 Vom Compiler wird Prolog\- und Epilogcode zum Speichern und Wiederherstellen von ESI\-, EDI\-, EBX\- sowie EBP\-Registern verwendet, sofern sie in der Funktion verwendet werden.  
  
> [!NOTE]
>  Wenn eine Struktur, Union oder Klasse nach Wert aus einer Funktion zurückgegeben wird, müssen alle Definitionen des Typs identisch sein, andernfalls können zur Laufzeit Fehler im Programm auftreten.  
  
 Informationen zur Definition von eigenem Prolog\- und Epilogcodes in Funktionen finden Sie unter [Naked\-Funktionsaufrufe](../cpp/naked-function-calls.md).  
  
 Weitere Informationen zu Standardaufrufkonventionen im Code, der auf x64\-Plattformen abzielt, finden Sie unter [Übersicht über x64\-Aufrufkonventionen](../build/overview-of-x64-calling-conventions.md).  Weitere Informationen zu Aufrufkonventionsproblemen im Code, der auf ARM\-Plattformen abzielt, finden Sie unter [Häufig auftretende ARM\-Migrationsprobleme bei Visual C\+\+](../build/common-visual-cpp-arm-migration-issues.md).  
  
 Die folgenden Aufrufkonventionen werden vom Visual C\/C\+\+\-Compiler unterstützt.  
  
|Schlüsselwort|Stapelcleanup|Parameterübergabe|  
|-------------------|-------------------|-----------------------|  
|[\_\_cdecl](../cpp/cdecl.md)|Aufrufer|Schiebt Parameter in umgekehrter Reihenfolge \(von rechts nach links\) auf den Stapel|  
|[\_\_clrcall](../cpp/clrcall.md)|nicht verfügbar|Parameter der Reihe nach \(von links nach rechts\) auf den CLR\-Ausdrucksstapel laden.|  
|[\_\_stdcall](../cpp/stdcall.md)|Aufgerufener|Schiebt Parameter in umgekehrter Reihenfolge \(von rechts nach links\) auf den Stapel|  
|[\_\_fastcall](../cpp/fastcall.md)|Aufgerufener|Wird in Registern gespeichert und dann auf dem Stapel abgelegt|  
|[\_\_thiscall](../cpp/thiscall.md)|Aufgerufener|Wird auf den Stapel geschoben; der **this**\-Zeiger wird in ECX gespeichert|  
|[\_\_vectorcall](../cpp/vectorcall.md)|Aufgerufener|Wird in Registern gespeichert und anschließend in umgekehrter Reihenfolge auf dem Stapel abgelegt \(rechts nach links\)|  
  
 Weitere Informationen finden Sie unter [Veraltete Aufrufkonventionen](../cpp/obsolete-calling-conventions.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)