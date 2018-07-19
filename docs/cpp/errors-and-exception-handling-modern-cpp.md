---
title: Fehler- und Ausnahmebehandlung (modernes C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee05e7008795056ee197ce45f68084e6c633f23c
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939740"
---
# <a name="errors-and-exception-handling-modern-c"></a>Behandeln von Fehlern und Ausnahmen (Modern C++)
In modernem C++ ist in den meisten Szenarien die Verwendung von Ausnahmen die bevorzugte Methode zum Mitteilen und Behandeln von logischen Fehlern und Laufzeitfehler. Dies gilt besonders, wenn der Stapel möglicherweise einige Funktionsaufrufe zwischen der Funktion enthält, die den Fehler entdeckt, und der Funktion, die über den Kontext für die Fehlerbehandlung verfügt. Ausnahmen stellen eine formale, gut definierte Methode für den Code bereit, der Fehler erkennt, um die Informationen an die Aufrufliste (call stack) zu übergeben.  
  
 Programmfehler werden in zwei Kategorien unterteilt: Logische Fehler, die auf Programmierfehlern beruhen, wie beispielsweise der Fehler "Index außerhalb des gültigen Bereichs", und Laufzeitfehler, die nicht der Kontrolle des Programmierers unterliegen, wie beispielsweise der Fehler "Netzwerk nicht verfügbar". In der C-Programmierung sowie in COM erfolgt die Benachrichtigung über Fehler entweder durch Rückgabe eines Werts, der einen Fehlercode oder einen Statuscode für eine bestimmte Funktion darstellt, oder durch Festlegung einer globalen Variablen, die der Aufrufer nach jedem Funktionsaufruf abrufen kann, um festzustellen, ob Fehler gemeldet wurden. Beispielsweise wird in der COM-Programmierung der HRESULT-Rückgabewert verwendet, um dem Aufrufer einen Fehler mitzuteilen, und die Win32-API enthält die GetLastError-Funktion, die den letzten Fehler abrufen kann, der von der Aufrufliste gemeldet wurde. In beiden Fällen liegt es beim Aufrufer, den Code zu erkennen und darauf entsprechend zu reagieren. Wenn der Aufrufer den Fehlercode nicht explizit behandelt, kann das Programm ohne Warnung abstürzen, oder es wird mit ungültigen Daten fortgesetzt und produziert falsche Ergebnisse.  
  
 Ausnahmen werden in modernem C++ aus folgenden Gründen verwendet:  
  
-   Eine Ausnahme erzwingt, dass der aufrufende Code eine Fehlerbedingung erkennt und behandelt. Nicht behandelte Ausnahmen beenden die Programmausführung.  
  
-   Einer Ausnahme springt zu der Position in der Aufrufliste, an welcher der Fehler behandelt werden kann. Zwischenfunktionen können die Ausnahme weitergeben. Sie müssen nicht für die Koordination mit anderen Ebenen sorgen.  
  
-   Nachdem eine Ausnahme ausgelöst wurde, zerstört der Entlademechanismus für den Ausnahmenstapel alle Objekte im Gültigkeitsbereich nach genau definierten Regeln.  
  
-   Eine Ausnahme ermöglicht die saubere Trennung zwischen dem Code, der den Fehler erkennt, und dem Code, der den Fehler behandelt.  
  
 Das folgende vereinfachende Beispiel zeigt die notwendige Syntax zum Auslösen und Abfangen von Ausnahmen in C++.  
  
```cpp  
#include <stdexcept>  
#include <limits>  
#include <iostream>  
  
using namespace std;  
class MyClass  
{  
public:  
   void MyFunc(char c)  
   {  
      if(c > numeric_limits<char>::max())  
         throw invalid_argument("MyFunc argument too large.");  
      //...  
   }  
};  
  
int main()  
{  
   try  
   {  
      MyFunc(256); //cause an exception to throw  
   }  
  
   catch(invalid_argument& e)  
   {  
      cerr << e.what() << endl;  
      return -1;  
   }  
   //...  
   return 0;  
}  
  
```  
  
 Ausnahmen in C++ ähneln denen in Sprachen wie C# und Java. In der **versuchen Sie es** blockieren, wenn eine Ausnahme ist *ausgelöst* wird *abgefangen* vom ersten zugehörigen **catch** Block, dessen Typ, die von übereinstimmt, der Diese Ausnahme. Das heißt, springt die Ausführung von der **auslösen** Anweisung, um die **catch** Anweisung. Ist kein verwendbarer catch-Block vorhanden, wird `std::terminate` aufgerufen und das Programm beendet. In C++ kann jeder Typ ausgelöst werden. Es wird jedoch empfohlen, einen Typ auslösen, der direkt oder indirekt von `std::exception` abgeleitet ist. Im vorherigen Beispiel der Ausnahmetyp, [Invalid_argument](../standard-library/invalid-argument-class.md), wird in der Standardbibliothek in definiert die [ \<Stdexcept >](../standard-library/stdexcept.md) Headerdatei. C++ stellt keine bereit und ist nicht erforderlich, eine **schließlich** Block, um sicherzustellen, dass alle Ressourcen freigegeben werden, wenn eine Ausnahme ausgelöst wird. Die RAII-Technik (Resource Acquisition Is Initialization, Ressourcenbelegung ist Initialisierung), die intelligente Zeiger verwendet, bietet die erforderliche Funktionalität zur Ressourcenbereinigung. Weitere Informationen finden Sie unter [Vorgehensweise: Entwurf für die Ausnahmesicherheit](../cpp/how-to-design-for-exception-safety.md). Weitere Informationen über die C++-stapelentlademechanismus finden Sie unter [Ausnahmen und Stapel entladen](../cpp/exceptions-and-stack-unwinding-in-cpp.md).  
  
## <a name="basic-guidelines"></a>Grundlegende Richtlinien  
 Stabile Fehlerbehandlung ist in jeder Programmiersprache schwierig. Obwohl Ausnahmen etliche Features bereitstellen, die gute Fehlerbehandlung unterstützen, können sie Ihnen nicht die gesamte Arbeit abnehmen. Um die Vorteile des Ausnahmemechanismus auszuschöpfen, sollten Sie Ausnahmen bei der Entwicklung Ihres Codes einplanen.  
  
-   Verwenden Sie Assertionen, um Fehler zu verhindern, die nie auftreten sollten. Verwenden Sie Ausnahmen, um Fehler abzufangen, die beispielsweise bei der Eingabevalidierung oder in Parametern von öffentlichen Funktionen auftreten können. Weitere Informationen finden Sie im Abschnitt **Ausnahmen Vs. Assertionen**.  
  
-   Verwenden Sie Ausnahmen, wenn der Code, der den Fehler behandelt, durch einen oder mehrere eingeschobene Funktionsaufrufe von dem Code getrennt ist, der den Fehler erkennt. Erwägen Sie, Fehlercodes statt leistungskritischer Schleifen zu verwenden, wenn der Code, der den Fehler behandelt, eng mit dem Code gekoppelt ist, der den Fehler erkennt. 
  
-   Für jede Funktion, die eine Ausnahme auslösen oder verteilen kann, sollten Sie eine der drei Ausnahmegarantien bereitstellen: die starke Garantie, die grundlegende Garantie oder die Nothrow (Noexcept)-Garantie. Weitere Informationen finden Sie unter [Vorgehensweise: Entwurf für die Ausnahmesicherheit](../cpp/how-to-design-for-exception-safety.md).  
  
-   Lösen Sie Ausnahmen per Wert aus, fangen Sie Ausnahmen per Referenz ab. Fangen Sie nicht ab, was Sie nicht behandeln können. 
  
-   Verwenden Sie keine Ausnahmespezifikationen; sie sind seit C++11 veraltet. Weitere Informationen finden Sie im Abschnitt **Ausnahmespezifikationen und Noexcept**.  
  
-   Verwenden Sie wenn möglich Ausnahmetypen der Standardbibliothek. Leiten Sie benutzerdefinierte Ausnahmetypen aus der [Exception-Klasse](../standard-library/exception-class.md) Hierarchie.  
  
-   Lassen Sie Ausnahmen nicht von Destruktoren oder Funktionen zur Speicherfreigabe auslösen.  
  
## <a name="exceptions-and-performance"></a>Ausnahmen und Leistungsfähigkeit  
 Der Ausnahmemechanismus verursacht nur sehr geringe Leistungseinbußen, wenn keine Ausnahme ausgelöst wird. Wenn eine Ausnahme ausgelöst wird, sind die Kosten für Stapeldurchlauf und -Entladung ungefähr mit den Kosten eines Funktionsaufrufs vergleichbar. Zusätzliche Datenstrukturen sind erforderlich, um die Aufrufliste nach Nachverfolgen einer **versuchen** Block erreicht wird, und zusätzliche Anweisungen sind erforderlich, um den Stapel zu entladen, wenn eine Ausnahme ausgelöst wird. Trotzdem sind in den meisten Szenarien die entsprechenden Leistungseinbußen und der Speicherbedarf nicht signifikant. Die nachteilige Auswirkung von Ausnahmen auf die Leistung ist wahrscheinlich nur auf Systemen mit sehr eingeschränktem Arbeitsspeicher von Bedeutung, oder in leistungskritischen Schleifen, in denen ein Fehler wahrscheinlich wiederkehrend auftritt, und in denen der den Fehler behandelnde Code eng mit dem Code gekoppelt ist, der den Fehler mitteilt. In jedem Fall ist es unmöglich, die Effektivkosten von Ausnahmen ohne Codeprofilierung und Messungen zu ermitteln. Auch in den seltenen Fällen, in denen die Kosten signifikant sind, sollten Sie abwägen, ob diese Kosten nicht die Vorteile rechtfertigen (wie korrekter Code, leichtere Verwaltbarkeit und andere), die von einer gut entworfenen Ausnahmerichtlinie sichergestellt werden.  
  
## <a name="exceptions-vs-assertions"></a>Ausnahmen und Assertionen  
 Ausnahmen und Assertionen sind zwei verschiedene Mechanismen zum Erkennen von Laufzeitfehlern in einem Programm. Verwenden Sie Assertionen, um während der Entwicklung Bedingungen zu ermitteln, die niemals zutreffen dürfen, wenn der gesamte Code fehlerfrei ist. Es gibt keine Möglichkeit, einen solchen Fehler mit einer Ausnahme zu behandeln, weil der Fehler darauf hinweist, dass etwas im Code behoben werden muss. Der Fehler stellt keine Bedingung dar, die das Programm zur Laufzeit beheben muss. Eine Assertion beendet die Ausführung in der Anweisung, damit Sie den Programmzustand im Debugger überprüfen können. Dagegen setzt eine Ausnahme die Programmausführung bis zum ersten entsprechenden catch-Handler fort. Verwenden Sie Ausnahmen, um Fehlerbedingungen zu überprüfen, die zur Laufzeit auftreten können (beispielsweise "Datei nicht gefunden" oder "Nicht genügend Arbeitsspeicher"), auch wenn der Code korrekt ist. Sie sollten die Programmausführung nach solchen Bedingungen nicht sofort beenden, sondern vorher zumindest noch eine entsprechende Meldung in eine Protokolldatei schreiben. Überprüfen Sie immer Argumente für öffentliche Funktionen mithilfe von Ausnahmen. Auch wenn die Funktion fehlerfrei ist, haben Sie möglicherweise keine vollständige Kontrolle über die Argumente, die ein Benutzer übergibt.  
  
## <a name="c-exceptions-versus-windows-seh-exceptions"></a>C++-Ausnahmen und Windows SEH-Ausnahmen  
 Sowohl C-Programme als auch C++-Programme können den Mechanismus der strukturierten Ausnahmebehandlung (Structured Exception Handling, SEH) im Windows-Betriebssystem verwenden. Die Konzepte in SEH entsprechen denen für C++-Ausnahmen, außer dass SEH verwendet die `__try`, `__except`, und `__finally` anstelle von erstellt **versuchen** und **catch**. In Visual C++ werden C++-Ausnahmen für SEH implementiert. Wenn Sie jedoch C++-Code schreiben, verwenden Sie die Syntax für C++-Ausnahmen.  
  
 Weitere Informationen zu SEH finden Sie unter [Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md).  
  
## <a name="exception-specifications-and-noexcept"></a>Ausnahmespezifikationen und noexcept  
 Ausnahmespezifikationen wurden in C++ als Möglichkeit eingeführt, um die Ausnahmen festzulegen, die eine Funktion auslösen kann. Ausnahmespezifikationen haben sich in der Praxis jedoch als problematisch herausgestellt und wurden im Normenentwurf C++11 als veraltet gekennzeichnet. Es wird empfohlen, dass Sie keine Ausnahmespezifikationen mit Ausnahme von verwenden `throw()`, was bedeutet, dass die Funktion keine Ausnahmen ermöglicht. Bei Verwendung von Ausnahmespezifikationen des Typs muss `throw(` *Typ*`)`, beachten Sie, dass Visual C++ weicht, aus dem Standard auf bestimmte Weise insofern. Weitere Informationen finden Sie unter [Ausnahmespezifikationen (Throw)](../cpp/exception-specifications-throw-cpp.md). Der Bezeichner `noexcept` wird in C++11 als die bevorzugte Alternative zu `throw()` eingeführt.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Schnittstelle zwischen Code von nicht- Ausnahmen](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)   
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Language Reference (C++-Programmiersprachenreferenz)](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
