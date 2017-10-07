---
title: Wiederholen Sie den-except-Anweisung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- EXCEPTION_CONTINUE_SEARCH
- _exception_info
- __except
- EXCEPTION_CONTINUE_EXECUTION
- _exception_code
- __except_cpp
- _exception_info_cpp
- EXCEPTION_EXECUTE_HANDLER
- _abnormal_termination
dev_langs:
- C++
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: e7a9b4aebd0ae60feeedc64644d3e50b8859f7cf
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="try-except-statement"></a>try-except-Anweisung
**Microsoft-spezifisch**  
  
 Die folgende Syntax beschreibt eine try-except-Anweisung:  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="remarks"></a>Hinweise  
 Die **versuchen-mit Ausnahme von** -Anweisung ist eine Microsoft-Erweiterung für den C und C++-Sprachen, die es zielanwendungen erhalten zu steuern, wann Ereignisse, die normalerweise zur Beendigung des Programms auftreten. Diese Ereignisse werden als Ausnahmen bezeichnet, und der Mechanismus, der die Ausnahmen behandelt, wird als strukturierte Ausnahmebehandlung bezeichnet.  
  
 Weitere Informationen finden Sie unter der [Try-finally-Anweisung](../cpp/try-finally-statement.md).  
  
 Ausnahmen können entweder hardwarebasiert oder softwarebasiert sein. Auch wenn Anwendungen nicht von Hardware- oder Softwareausnahmen vollständig wiederhergestellt werden können, kann die strukturierte Ausnahmebehandlung das Anzeigen von Fehlerinformationen ermöglichen und den internen Zustand der Anwendung abfangen, um das Problem zu diagnostizieren. Dies ist besonders hilfreich bei zeitweilig auftretenden Problemen, die nicht leicht reproduziert werden können.  
  
> [!NOTE]
>  Die strukturierte Ausnahmebehandlung arbeitet mit Win32 für C- und C++-Quelldateien. Sie ist jedoch nicht speziell für C++ entwickelt. Sie können sicherstellen, dass der Code portabler ist, indem Sie die C++-Ausnahmebehandlung verwenden. Die C++-Ausnahmebehandlung ist auch flexibler, da sie Ausnahmen eines beliebigen Typs behandeln kann. Für C++-Programme wird empfohlen, dass Sie den C++ Mechanismus zur Ausnahmebehandlung verwenden ([versuchen, catch- und throw-](../cpp/try-throw-and-catch-statements-cpp.md) Anweisungen).  
  
 Die Verbundanweisung nach der `__try`-Klausel ist der Text bzw. der geschützte Bereich. Die Verbundanweisung nach der `__except`-Klausel ist der Ausnahmehandler. Der Handler gibt eine Reihe von Aktionen an, die abgerufen werden, wenn eine Ausnahme während der Ausführung des Texts des geschützten Bereichs ausgelöst wird. Die Ausführung erfolgt folgendermaßen:  
  
1.  Der geschützte Bereich wird ausgeführt.  
  
2.  Wenn keine Ausnahme während der Ausführung des geschützten Bereichs auftritt, wird die Ausführung mit der Anweisung nach der `__except`-Klausel fortgesetzt.  
  
3.  Wenn eine Ausnahme, während der Ausführung des abgesicherten Abschnitts auftritt oder in einer Routine der geschützte Bereich aufruft, die `__except` *Ausdruck* (aufgerufen, die *Filter* Ausdruck) ausgewertet wird und der Wert Bestimmt, wie die Ausnahme behandelt wird. Es gibt drei Werte:  
  
     **EXCEPTION_CONTINUE_EXECUTION (-1)** Ausnahme wurde verworfen. Fortsetzen der Ausführung an der Stelle, an der die Ausnahme aufgetreten ist.  
  
     **EXCEPTION_CONTINUE_SEARCH (0)** Ausnahme wurde nicht erkannt. Fahren Sie fort, im Stapel nach einem Handler zu suchen, zuerst nach enthaltenen **try-except**-Anweisungen, dann nach Handlern mit der nächst höheren Priorität.  
  
     **Exception_execute_handler (1)** Ausnahme wurde erkannt. Übertragen Sie die Steuerung an den Ausnahmehandler, indem Sie die `__except`-Verbundanweisung ausführen und anschließend die Ausführung nach dem `__except`-Block fortsetzen.  
  
 Da der __**außer** -Ausdruck als C-Ausdruck ausgewertet wird, wird er auf einen einzelnen Wert, den bedingten Ausdrucksoperator oder den Komma-Operators beschränkt. Wenn eine erweiterte Verarbeitung erforderlich ist, kann der Ausdruck eine Routine aufrufen, die einen der drei Werte zurückgibt, die oben aufgelistet sind.  
  
 Jede Anwendung kann einen eigenen Ausnahmehandler haben.  
  
 Es ist nicht zulässig, in eine `__try`-Anweisung zu springen, wohingegen das Herausspringen aus einer solchen zulässig ist. Der Ausnahmehandler wird nicht aufgerufen, wenn ein Prozess, während der Ausführung beendet wird einer **versuchen-mit Ausnahme von** Anweisung.  
  
 Weitere Informationen finden Sie im Knowledge Base-Artikel Q315937: Gewusst wie: Blockierstapelüberlauf in einer Visual C++-Anwendung.  
  
## <a name="the-leave-keyword"></a>Das __leave-Schlüsselwort  
 Das `__leave`-Schlüsselwort ist nur im abgesicherten Abschnitt einer `try-except`-Anweisung gültig. Als Resultat wird zum Ende des abgesicherten Abschnitts gesprungen. Die Ausführung wird mit der ersten Anweisung nach dem Ausnahmehandler fortgesetzt.  
  
 Eine `goto`-Anweisung kann auch aus dem geschützten Bereich herausspringen, und die Leistung wird nicht beeinträchtigt wie in einer `try-finally`-Anweisung, da keine Stapelentladung auftritt. Es empfiehlt sich jedoch, dass Sie das `__leave`-Schlüsselwort statt einer `goto`-Anweisung verwenden, da es so wahrscheinlich seltener zu einem Programmierfehler kommt, wenn der geschützte Bereich groß oder komplex ist.  
  
### <a name="structured-exception-handling-intrinsic-functions"></a>Intrinsische Funktionen der strukturierten Ausnahmebehandlung  
 Strukturierte Ausnahmebehandlung bietet zwei intrinsische Funktionen, die für die Verwendung mit verfügbar sind die **versuchen-mit Ausnahme von** Anweisung: **GetExceptionCode** und **GetExceptionInformation**.  
  
 **GetExceptionCode** gibt der Code (32-Bit-Ganzzahl) der Ausnahme zurück.  
  
 Die systeminterne Funktion **GetExceptionInformation** gibt einen Zeiger auf eine Struktur mit zusätzlichen Informationen zur Ausnahme. Mit diesem Zeiger können Sie auf den Computerzustand zugreifen, der zum Zeitpunkt einer Hardwareausnahme vorhanden war. Die Struktur lautet wie folgt:  
  
```  
struct _EXCEPTION_POINTERS {  
      EXCEPTION_RECORD *ExceptionRecord,  
      CONTEXT *ContextRecord }  
```  
  
 Die Zeigertypen**EXCEPTION_RECORD** und \_ **Kontext** in der Includedatei EXCPT definiert sind. H.  
  
 Sie können **GetExceptionCode** innerhalb des ausnahmehandlers. Sie können jedoch **GetExceptionInformation** nur innerhalb des ausnahmefilterausdrucks. Die Information, auf die verwiesen wird, befindet sich im Allgemeinen auf dem Stapel und ist nicht mehr verfügbar, wenn die Steuerung an den Ausnahmehandler übertragen wird.  
  
 Die systeminterne Funktion **AbnormalTermination** ist innerhalb eines beendigungshandlers zur Verfügung. Sie gibt 0 zurück, wenn der Text der `try-finally`-Anweisung nacheinander beendet wird. In allen anderen Fällen wird 1 zurückgegeben.  
  
 EXCPT.H definiert mehrere alternative Namen für diese systeminternen Funktionen:  
  
 **GetExceptionCode** entspricht _exception_code  
  
 **GetExceptionInformation** entspricht _exception_info  
  
 **AbnormalTermination** entspricht _abnormal_termination  
  
## <a name="example"></a>Beispiel  
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
  
 `int* p = 0x00000000;   // pointer to NULL`  
  
 `puts("hello");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `__try{`  
  
 `puts("in try");`  
  
 `*p = 13;    // causes an access violation exception;`  
  
 `}__finally{`  
  
 `puts("in finally. termination: ");`  
  
 `puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");`  
  
 `}`  
  
 `}__except(filter(GetExceptionCode(), GetExceptionInformation())){`  
  
 `puts("in except");`  
  
 `}`  
  
 `puts("world");`  
  
 `}`  
  
## <a name="output"></a>Ausgabe  
  
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
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
