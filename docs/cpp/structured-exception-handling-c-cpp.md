---
title: Structured Exception Handling (C/C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1edcf2cb24273f475b1ba98e5e973f5704c0cec8
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461701"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)
Obwohl bei Windows und Visual C++ die strukturierte Ausnahmebehandlung (SEH) unterstützt wird, ist die Verwendung der ISO-Standard-C++-Ausnahmebehandlung empfehlenswert, da Code damit besser portierbar und flexibler ist. Trotzdem ist die Verwendung von SEH in vorhandenem Code oder für bestimmte Arten von Programmen möglicherweise erforderlich.  
  
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
  
## <a name="grammar"></a>Grammatik  
 *Try-except-Anweisung* :  
  
 `__try` *Compound-statement*  
  
 `__except` ( `expression` ) *Compound-Statement*  
  
## <a name="remarks"></a>Hinweise  
 Mit SEH kann sichergestellt werden, dass Ressourcen wie Speicherblöcke und Dateien bei einer unerwarteten Beendigung der Ausführung ordnungsgemäß funktionieren. Sie können auch bestimmte Probleme behandeln, z. B. unzureichender Arbeitsspeicher – mithilfe von kurzem strukturiertem Code, der nicht abhängig ist **Goto** -Anweisungen oder ausführliche Tests von Rückgabecodes.  
  
 Die Anweisungen try-except und try-finally, auf die sich dieser Artikel bezieht, sind Microsoft-Erweiterungen der Programmiersprache C. Sie unterstützen SEH, indem es Anwendungen ermöglicht wird, die Steuerung eines Programms nach Ereignissen abzurufen, die andernfalls das Beenden der Ausführung zur Folge haben würden. Obwohl SEH mit C++-Quelldateien funktioniert, ist sie nicht ausdrücklich für C++ vorgesehen. Wenn Sie SEH in einem C++-Programm verwenden, die Sie bei der Kompilierung der [/EH](../build/reference/eh-exception-handling-model.md) Option – zusammen mit bestimmten Modifizierern – Destruktoren für lokale Objekte aufgerufen werden, aber weitere Ausführungsverhalten entspricht möglicherweise nicht Ihren Erwartungen. (Eine Abbildung finden Sie im Beispiel weiter unten in diesem Artikel). In den meisten Fällen anstelle von SEH empfiehlt es sich, dass Sie die ISO-Standard verwenden [C++-Ausnahmebehandlung](../cpp/try-throw-and-catch-statements-cpp.md), die auch Visual C++ unterstützt. Mithilfe der C++-Ausnahmebehandlung können Sie eine bessere Portierbarkeit des Codes sicherstellen, und Sie können Ausnahmen jeglichen Typs behandeln.  
  
 C-Modulen, bei denen SEH verwendet wird, können mit C++-Modulen kombiniert werden, bei denen C++-Ausnahmebehandlung verwendet wird. Weitere Informationen finden Sie unter [Unterschiede bei der Ausnahmebehandlung](../cpp/exception-handling-differences.md).  
  
 Es gibt zwei SEH-Mechanismen:  
  
-   [Ausnahmehandler](../cpp/writing-an-exception-handler.md), die reagieren kann, oder die Ausnahme zu schließen.  
  
-   [Beendigungshandler](../cpp/writing-a-termination-handler.md), die aufgerufen werden, wenn eine Ausnahme beenden in einem Codeblock verursacht.  
  
 Diese beiden Arten von Handlern unterscheiden sich zwar, sind allerdings hinsichtlich eines als "Entladen des Stapels" bekannten Prozesses eng miteinander verknüpft. Wenn eine Ausnahme auftritt, wird von Windows der zuletzt installierte Ausnahmehandler gesucht, der gerade aktiv ist. Beim Handler kann eine von drei Möglichkeiten auftreten:  
  
-   Fehler beim Erkennen der Ausnahme und Übergabe des Steuerelements an andere Handler  
  
-   Erkennen der Ausnahme, diese aber zurückweisen  
  
-   Erkennen und behandeln der Ausnahme  
  
 Der Ausnahmehandler, der die Ausnahme erkennt, befindet sich möglicherweise nicht in der Funktion, die bei Auftreten der Ausnahme ausgeführt wurde. In einigen Fällen ist es möglicherweise in einer Funktion wesentlich höher auf dem Stapel. Die gegenwärtig ausgeführte Funktion sowie alle weiteren Funktionen im Stapelrahmen werden beendet. Der Stapel ist während dieses Vorgangs "entlädt sich", also lokale Variablen von beendeten Funktionen – es sei denn, sie sind **statische**– aus dem Stapel gelöscht werden.  
  
 Beim Entladen des Stapels ruft das Betriebssystem alle Beendigungshandler auf, die Sie für jede Funktion geschrieben haben. Mit einem Beendigungshandler können Sie Ressourcen bereinigen, die andernfalls bei einer nicht ordnungsgemäßen Beendigung geöffnet bleiben würden. Wenn Sie einen kritischen Abschnitt erreichen, können Sie in den Beendigungshandler beenden. Wenn das Programm beendet werden soll, können Sie weitere Ordnungsaufgaben, z. B. das Schließen und Entfernen von temporären Dateien, ausführen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)  
  
-   [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)  
  
-   [Verwendung einer strukturieren Ausnahmebehandlung mit C++](../cpp/using-structured-exception-handling-with-cpp.md)  
  
## <a name="example"></a>Beispiel  
 Wie bereits erwähnt werden Destruktoren für lokale Objekte aufgerufen, wenn SEH in einem C++-Programm verwendet und mithilfe der `/EH` - Option sowie gewissen Modifizierern, z. B. `/EHsc` und `/EHa` kompiliert wird. Allerdings entspricht das Verhalten während der Ausführung bei zusätzlicher Verwendung von C++-Ausnahmen möglicherweise nicht Ihren Erwartungen. Im folgenden Beispiel werden diese unterschiedlichen Verhaltensweisen veranschaulicht.  
  
```cpp  
#include <stdio.h>  
#include <Windows.h>  
#include <exception>  
  
class TestClass  
{  
public:  
    ~TestClass()  
    {  
        printf("Destroying TestClass!\r\n");  
    }  
};  
  
__declspec(noinline) void TestCPPEX()  
{  
#ifdef CPPEX  
    printf("Throwing C++ exception\r\n");  
    throw std::exception("");  
#else  
    printf("Triggering SEH exception\r\n");  
    volatile int *pInt = 0x00000000;  
    *pInt = 20;  
#endif  
}  
  
__declspec(noinline) void TestExceptions()  
{  
    TestClass d;  
    TestCPPEX();  
}  
  
int main()  
{  
    __try  
    {  
        TestExceptions();  
    }  
    __except(EXCEPTION_EXECUTE_HANDLER)  
    {  
        printf("Executing SEH __except block\r\n");  
    }  
  
    return 0;  
}  
```  
  
 Bei Verwendung von **/EHsc** kompiliert diesen Code aber das Steuerelement für die lokalen Tests `CPPEX` ist nicht definiert ist, besteht keine Ausführung von der `TestClass` Destruktor und die Ausgabe sieht wie folgt:  
  
```Output  
Triggering SEH exception  
Executing SEH __except block  
```  
  
 Bei Verwendung von **/EHsc** zum Kompilieren des Codes und `CPPEX` wird mittels definiert `/DCPPEX` (sodass eine C++-Ausnahme ausgelöst wird), wird die `TestClass` Destruktor ausgeführt und die Ausgabe sieht wie folgt aus:  
  
```Output  
Throwing C++ exception  
Destroying TestClass!  
Executing SEH __except block  
```  
  
 Bei Verwendung von **/EHa** zum Kompilieren des Codes, der `TestClass` Destruktor ausgeführt wird, unabhängig davon, ob die Ausnahme ausgelöst wurde, mithilfe von `std::throw` oder mit SEH zum Auslösen der Ausnahme (`CPPEX` oder nicht definiert). Die Ausgabe sieht wie folgt aus:  
  
```Output  
Throwing C++ exception  
Destroying TestClass!  
Executing SEH __except block  
```  
  
 Weitere Informationen finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../build/reference/eh-exception-handling-model.md).  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [\<exception>](../standard-library/exception.md)   
 [Fehler- und Ausnahmebehandlung](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Strukturierte Ausnahmebehandlung (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)