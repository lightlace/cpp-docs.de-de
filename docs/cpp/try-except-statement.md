---
title: "try-except-Anweisung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_abnormal_termination_cpp"
  - "_exception_code_cpp"
  - "EXCEPTION_CONTINUE_SEARCH"
  - "_exception_info"
  - "__except"
  - "EXCEPTION_CONTINUE_EXECUTION"
  - "_exception_code"
  - "__except_cpp"
  - "_exception_info_cpp"
  - "EXCEPTION_EXECUTE_HANDLER"
  - "_abnormal_termination"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__try-Schlüsselwort [C++]"
  - "_abnormal_termination-Schlüsselwort [C++]"
  - "_exception_code-Schlüsselwort [C++]"
  - "_exception_info-Schlüsselwort [C++]"
  - "EXCEPTION_CONTINUE_EXECUTION-Makro"
  - "EXCEPTION_CONTINUE_SEARCH-Makro"
  - "EXCEPTION_EXECUTE_HANDLER-Makro"
  - "GetExceptionCode-Funktion"
  - "try-catch-Schlüsselwort [C++], try-except-Schlüsselwort [C++]"
  - "try-except-Schlüsselwort [C++]"
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# try-except-Anweisung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Die folgende Syntax beschreibt eine try\-except\-Anweisung:  
  
## Syntax  
  
```  
  
      __try   
{  
   // guarded code  
}  
__except ( expression )  
{  
   // exception handler code  
}  
```  
  
## Hinweise  
 Die **try\-except**\-Anweisung ist eine Microsoft\-Erweiterung zu den Programmiersprachen C und C\+\+, die es Zielanwendungen ermöglicht, die Steuerung zu übernehmen, wenn Ereignisse auftreten, die normalerweise zur Beendigung des Programms führen.  Diese Ereignisse werden als Ausnahmen bezeichnet, und der Mechanismus, der die Ausnahmen behandelt, wird als strukturierte Ausnahmebehandlung bezeichnet.  
  
 Weitere Informationen finden Sie unter der [try\-finally\-Anweisung](../cpp/try-finally-statement.md).  
  
 Ausnahmen können entweder hardwarebasiert oder softwarebasiert sein.  Auch wenn Anwendungen nicht von Hardware\- oder Softwareausnahmen vollständig wiederhergestellt werden können, kann die strukturierte Ausnahmebehandlung das Anzeigen von Fehlerinformationen ermöglichen und den internen Zustand der Anwendung abfangen, um das Problem zu diagnostizieren.  Dies ist besonders hilfreich bei zeitweilig auftretenden Problemen, die nicht leicht reproduziert werden können.  
  
> [!NOTE]
>  Die strukturierte Ausnahmebehandlung arbeitet mit Win32 für C\- und C\+\+\-Quelldateien.  Sie ist jedoch nicht speziell für C\+\+ entwickelt.  Sie können sicherstellen, dass der Code portabler ist, indem Sie die C\+\+\-Ausnahmebehandlung verwenden.  Die C\+\+\-Ausnahmebehandlung ist auch flexibler, da sie Ausnahmen eines beliebigen Typs behandeln kann.  Für C\+\+\-Programme wird empfohlen, dass Sie den C\+\+\-Mechanismus zur Ausnahmebehandlung verwenden \([try\-, catch\- und throw](../cpp/try-throw-and-catch-statements-cpp.md)\-Anweisungen\).  
  
 Die Verbundanweisung nach der `__try`\-Klausel ist der Text bzw. der geschützte Bereich.  Die Verbundanweisung nach der `__except`\-Klausel ist der Ausnahmehandler.  Der Handler gibt eine Reihe von Aktionen an, die abgerufen werden, wenn eine Ausnahme während der Ausführung des Texts des geschützten Bereichs ausgelöst wird.  Die Ausführung erfolgt folgendermaßen:  
  
1.  Der geschützte Bereich wird ausgeführt.  
  
2.  Wenn keine Ausnahme während der Ausführung des geschützten Bereichs auftritt, wird die Ausführung mit der Anweisung nach der `__except`\-Klausel fortgesetzt.  
  
3.  Wenn während der Ausführung des geschützten Bereichs eine Ausnahme auftritt, oder in einer Routine, die der geschützte Bereich aufruft, wird der `__except`\-*Ausdruck* \(*filter*\-Ausdruck genannt\) ausgewertet, und der Wert bestimmt, wie die Ausnahme bearbeitet wird.  Es gibt drei Werte:  
  
     **EXCEPTION\_CONTINUE\_EXECUTION \(–1\)** Ausnahme wurde verworfen.  Fortsetzen der Ausführung an der Stelle, an der die Ausnahme aufgetreten ist.  
  
     **EXCEPTION\_CONTINUE\_SEARCH \(0\)** Ausnahme wurde nicht erkannt.  Fahren Sie fort, im Stapel nach einem Handler zu suchen, zuerst nach enthaltenen **try\-except**\-Anweisungen, dann nach Handlern mit der nächst höheren Priorität.  
  
     **EXCEPTION\_EXECUTE\_HANDLER \(1\)** Ausnahme wurde erkannt.  Übertragen Sie die Steuerung an den Ausnahmehandler, indem Sie die `__except`\-Verbundanweisung ausführen und anschließend die Ausführung nach dem `__except`\-Block fortsetzen.  
  
 Da der \_\_**except**\-Ausdruck als C\-Ausdruck ausgewertet wird, wird er auf einen Einzelwert, den bedingten Ausdrucksoperator oder den Kommaoperator beschränkt.  Wenn eine erweiterte Verarbeitung erforderlich ist, kann der Ausdruck eine Routine aufrufen, die einen der drei Werte zurückgibt, die oben aufgelistet sind.  
  
 Jede Anwendung kann einen eigenen Ausnahmehandler haben.  
  
 Es ist nicht zulässig, in eine `__try`\-Anweisung zu springen, wohingegen das Herausspringen aus einer solchen zulässig ist.  Der Ausnahmehandler wird nicht aufgerufen, wenn ein Vorgang in der Mitte der Ausführung einer **try\-except**\-Anweisung abgebrochen wird.  
  
 Weitere Informationen finden Sie im Knowledge Base\-Artikel Q315937: Gewusst wie: Blockierstapelüberlauf in einer Visual C\+\+\-Anwendung.  
  
## Das \_\_leave\-Schlüsselwort  
 Das `__leave`\-Schlüsselwort ist nur im abgesicherten Abschnitt einer `try-except`\-Anweisung gültig. Als Resultat wird zum Ende des abgesicherten Abschnitts gesprungen.  Die Ausführung wird mit der ersten Anweisung nach dem Ausnahmehandler fortgesetzt.  
  
 Eine `goto`\-Anweisung kann auch aus dem geschützten Bereich herausspringen, und die Leistung wird nicht beeinträchtigt wie in einer `try-finally`\-Anweisung, da keine Stapelentladung auftritt.  Es empfiehlt sich jedoch, dass Sie das `__leave`\-Schlüsselwort statt einer `goto`\-Anweisung verwenden, da es so wahrscheinlich seltener zu einem Programmierfehler kommt, wenn der geschützte Bereich groß oder komplex ist.  
  
### Systeminterne Funktionen der strukturierten Ausnahmebehandlung  
 Die strukturierte Ausnahmebehandlung bietet zwei systeminterne Funktionen, die mit der **try\-except**\-Anweisung verwendet werden können: **GetExceptionCode** und **GetExceptionInformation**.  
  
 **GetExceptionCode** gibt den Code \(eine 32\-Bit\-Ganzzahl\) der Ausnahme zurück.  
  
 Die systeminterne Funktion **GetExceptionInformation** gibt einen Zeiger an eine Struktur zurück, welche zusätzliche Information über die Ausnahme enthält.  Mit diesem Zeiger können Sie auf den Computerzustand zugreifen, der zum Zeitpunkt einer Hardwareausnahme vorhanden war.  Die Struktur lautet wie folgt:  
  
```  
struct _EXCEPTION_POINTERS {  
      EXCEPTION_RECORD *ExceptionRecord,  
      CONTEXT *ContextRecord }  
```  
  
 Die Zeigertypen **EXCEPTION\_RECORD** und **CONTEXT** werden in der Includedatei EXCPT.H. definiert.  
  
 Sie können **GetExceptionCode** innerhalb des Ausnahmehandlers verwenden.  Sie können jedoch **GetExceptionInformation** nur innerhalb des Ausnahmefilterausdrucks verwenden.  Die Information, auf die verwiesen wird, befindet sich im Allgemeinen auf dem Stapel und ist nicht mehr verfügbar, wenn die Steuerung an den Ausnahmehandler übertragen wird.  
  
 Die systeminterne Funktion **AbnormalTermination** steht innerhalb eines Beendigungshandlers zur Verfügung.  Sie gibt 0 zurück, wenn der Text der `try-finally`\-Anweisung nacheinander beendet wird.  In allen anderen Fällen wird 1 zurückgegeben.  
  
 EXCPT.H definiert mehrere alternative Namen für diese systeminternen Funktionen:  
  
 **GetExceptionCode** entspricht \_exception\_code  
  
 **GetExceptionInformation** entspricht \_exception\_info  
  
 **AbnormalTermination** entspricht \_abnormal\_termination  
  
## Beispiel  
 `// exceptions_try_except_Statement.cpp`  
  
 `// Example of try-except and try-finally statements`  
  
 `#include <stdio.h>`  
  
 `#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION`  
  
 `#include <excpt.h>`  
  
 `int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep) {`  
  
 `puts("in filter.");`  
  
 `if (code == EXCEPTION_ACCESS_VIOLATION) {`  
  
 `puts("caught AV as expected.");`  
  
 `return EXCEPTION_EXECUTE_HANDLER;`  
  
 `}`  
  
 `else {`  
  
 `puts("didn't catch AV, unexpected.");`  
  
 `return EXCEPTION_CONTINUE_SEARCH;`  
  
 `};`  
  
 `}`  
  
 `int main()`  
  
 `{`  
  
 `int* p = 0x00000000;   // pointer to NULL`  
  
 `puts("hello");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `*p = 13;    // causes an access violation exception;`  
  
 `}__finally{`  
  
 `puts("in finally. termination: ");`  
  
 `puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");`  
  
 `}`  
  
 `}__except(filter(GetExceptionCode(), GetExceptionInformation())){`  
  
 `puts("in except");`  
  
 `}`  
  
 `puts("world");`  
  
 `}`  
  
## Ausgabe  
  
```  
hello  
in try  
in try  
in filter.  
caught AV as expected.  
in finally. termination:  
        abnormal  
in except  
world  
```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)