---
title: "Strukturierte Ausnahmebehandlung (C/C++)"
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
  - "C++-Ausnahmebehandlung, Ausnahmehandler"
  - "C++-Ausnahmebehandlung, Beendigungshandler"
  - "Strukturierte Ausnahmebehandlung"
  - "Beendigungshandler, Ausnahmebehandlung in C++"
  - "try-catch-Schlüsselwort [C++], Ausnahmehandler"
  - "try-catch-Schlüsselwort [C++], Beendigungshandler"
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
caps.latest.revision: 14
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Strukturierte Ausnahmebehandlung (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obwohl bei Windows und Visual C\+\+ die strukturierte Ausnahmebehandlung \(SEH\) unterstützt wird, ist die Verwendung der ISO\-Standard\-C\+\+\-Ausnahmebehandlung empfehlenswert, da Code damit besser portierbar und flexibler ist.  Trotzdem ist die Verwendung von SEH in vorhandenem Code oder für bestimmte Arten von Programmen möglicherweise erforderlich.  
  
## Microsoft\-spezifisch  
  
## Grammatik  
 *try\-except\-statement* :  
  
 `__try` *compound\-statement*  
  
 `__except` \( `expression` \) *compound\-statement*  
  
## Hinweise  
 Mit SEH kann sichergestellt werden, dass Ressourcen wie Speicherblöcke und Dateien bei einer unerwarteten Beendigung der Ausführung ordnungsgemäß funktionieren.  Sie können bestimmte Probleme, z. B. unzureichender Arbeitsspeicher, mithilfe von kurzem strukturiertem Code behandeln, in dem keine `goto`\-Anweisungen oder ausführliche Tests von Rückgabecodes verwendet werden.  
  
 Die Anweisungen try\-except und try\-finally, auf die sich dieser Artikel bezieht, sind Microsoft\-Erweiterungen der Programmiersprache C.  Sie unterstützen SEH, indem es Anwendungen ermöglicht wird, die Steuerung eines Programms nach Ereignissen abzurufen, die andernfalls das Beenden der Ausführung zur Folge haben würden.  Obwohl SEH mit C\+\+\-Quelldateien funktioniert, ist sie nicht ausdrücklich für C\+\+ vorgesehen.  Wenn Sie SEH in einem C\+\+\-Programm verwenden, das Sie mithilfe der [\/EH](../build/reference/eh-exception-handling-model.md) Option zusammen mit bestimmten Modifizierern kompilieren, werden Destruktoren für lokale Objekte aufgerufen. Das weitere Ausführungsverhalten entspricht allerdings möglicherweise nicht den Erwartungen.  \(Eine Abbildung finden Sie im Beispiel weiter unten in diesem Artikel\). In den meisten Fällen empfiehlt sich anstelle von SEH die Verwendung des ISO\-Standard für [C\+\+\-Ausnahmebehandlung](../cpp/try-throw-and-catch-statements-cpp.md), bei der auch Visual C\+\+ unterstützt wird.  Mithilfe der C\+\+\-Ausnahmebehandlung können Sie eine bessere Portierbarkeit des Codes sicherstellen, und Sie können Ausnahmen jeglichen Typs behandeln.  
  
 C\-Modulen, bei denen SEH verwendet wird, können mit C\+\+\-Modulen kombiniert werden, bei denen C\+\+\-Ausnahmebehandlung verwendet wird.  Weitere Informationen finden Sie unter [Unterschiede bei der Ausnahmebehandlung](../cpp/exception-handling-differences.md).  
  
 Es gibt zwei SEH\-Mechanismen:  
  
-   [Ausnahmehandler](../cpp/writing-an-exception-handler.md), die auf die Ausnahme reagieren kann oder sie zurückweist.  
  
-   [Beendigungshandler](../cpp/writing-a-termination-handler.md), die aufgerufen werden, wenn eine Ausnahme in einem Codeblock eine Beendigung verursacht.  
  
 Diese beiden Arten von Handlern unterscheiden sich zwar, sind allerdings hinsichtlich eines als "Entladen des Stapels" bekannten Prozesses eng miteinander verknüpft. Wenn eine Ausnahme auftritt, wird von Windows der zuletzt installierte Ausnahmehandler gesucht, der gerade aktiv ist.  Beim Handler kann eine von drei Möglichkeiten auftreten:  
  
-   Fehler beim Erkennen der Ausnahme und Übergabe des Steuerelements an andere Handler  
  
-   Erkennen der Ausnahme, diese aber zurückweisen  
  
-   Erkennen und behandeln der Ausnahme  
  
 Der Ausnahmehandler, der die Ausnahme erkennt, befindet sich möglicherweise nicht in der Funktion, die bei Auftreten der Ausnahme ausgeführt wurde.  In einigen Fällen ist es möglicherweise in einer Funktion wesentlich höher auf dem Stapel.  Die gegenwärtig ausgeführte Funktion sowie alle weiteren Funktionen im Stapelrahmen werden beendet.  Während dieses Vorgangs "entlädt sich" der Stapel. Lokale Variablen von beendeten Funktionen werden aus dem Stapel gelöscht, es sei denn, sie sind `static`.  
  
 Beim Entladen des Stapels ruft das Betriebssystem alle Beendigungshandler auf, die Sie für jede Funktion geschrieben haben.  Mit einem Beendigungshandler können Sie Ressourcen bereinigen, die andernfalls bei einer nicht ordnungsgemäßen Beendigung geöffnet bleiben würden.  Wenn Sie einen kritischen Abschnitt erreichen, können Sie in den Beendigungshandler beenden.  Wenn das Programm beendet werden soll, können Sie weitere Ordnungsaufgaben, z. B. das Schließen und Entfernen von temporären Dateien, ausführen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)  
  
-   [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)  
  
-   [Verwendung von strukturierter Ausnahmebehandlung in C\+\+](../cpp/using-structured-exception-handling-with-cpp.md)  
  
## Beispiel  
 Wie bereits erwähnt werden Destruktoren für lokale Objekte aufgerufen, wenn SEH in einem C\+\+\-Programm verwendet und mithilfe der **\/EH** \- Option sowie gewissen Modifizierern, z. B. **\/EHsc** und **\/EHa** kompiliert wird.  Allerdings entspricht das Verhalten während der Ausführung bei zusätzlicher Verwendung von C\+\+\-Ausnahmen möglicherweise nicht Ihren Erwartungen.  Im folgenden Beispiel werden diese unterschiedlichen Verhaltensweisen veranschaulicht.  
  
```cpp  
#include <stdio.h>  
#include <Windows.h>  
#include <exception>  
  
class TestClass  
{  
public:  
    ~TestClass()  
    {  
        printf("Destroying TestClass!\r\n");  
    }  
};  
  
__declspec(noinline) void TestCPPEX()  
{  
#ifdef CPPEX  
    printf("Throwing C++ exception\r\n");  
    throw std::exception("");  
#else  
    printf("Triggering SEH exception\r\n");  
    volatile int *pInt = 0x00000000;  
    *pInt = 20;  
#endif  
}  
  
__declspec(noinline) void TestExceptions()  
{  
    TestClass d;  
    TestCPPEX();  
}  
  
int main()  
{  
    __try  
    {  
        TestExceptions();  
    }  
    __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf("Executing SEH __except block\r\n");  
    }  
  
    return 0;  
}  
  
```  
  
 Wenn Sie **\/EHsc** zum Kompilieren dieses Codes verwenden, das lokale `CPPEX`\-Teststeuerelement nicht definiert ist, wird der `TestClass` \- Destruktor nicht ausgeführt, und die Ausgabe sieht wie folgt aus:  
  
  **Auslösen der SEH\-Ausnahme**  
**Ausführen des \_\_except\-SEH\-Blocks** Wenn Sie **\/EHsc** zum Kompilieren des Codes verwenden und `CPPEX` definiert mithilfe von `/DCPPEX` definiert wird \(damit eine C\+\+\-Ausnahme ausgelöst wird\), wird der `TestClass`\-Destruktor ausgeführt und die Ausgabe sieht wie folgt aus:  
  
  **Auslösen der C\+\+\-Ausnahme**  
**Zerstören von TestClass\!  Ausführen des \_\_except\-SEH\-Blocks**  Wenn Sie **\/EHa** zum Kompilieren des Codes verwenden, wird der `TestClass`\-Destruktor unabhängig davon ausgelöst, ob die Ausnahme mithilfe von `std::throw` oder mit SEH ausgelöst wurde, um die Ausnahme \(`CPPEX`\-definiert oder nicht\) auszulösen.  Die Ausgabe sieht wie folgt aus:  
  
  **Auslösen der C\+\+\-Ausnahme**  
**Zerstören von TestClass\!  Ausführen des \_\_except\-SEH\-Blocks**  Weitere Informationen finden Sie unter [\/EH \(Ausnahmebehandlungsmodell\)](../build/reference/eh-exception-handling-model.md).  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [\<exception\>](../standard-library/exception.md)   
 [Behandeln von Fehlern und Ausnahmen](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Strukturierte Ausnahmebehandlung \(Windows\)](http://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)