---
title: "Behandeln von Fehlern und Ausnahmen (Modern C++)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# Behandeln von Fehlern und Ausnahmen (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
      if(c < numeric_limits<char>::max())  
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
  
 Ausnahmen in C++ ähneln denen in Sprachen wie C# und Java. In der `try` zu blockieren, wenn eine Ausnahme ist *ausgelöst* werden *abgefangen* vom ersten zugehörigen `catch` Block, dessen Typ, der der Ausnahme entspricht. Das heißt, die Ausführung springt von der `throw`-Anweisung zur `catch`-Anweisung. Ist kein verwendbarer catch-Block vorhanden, wird `std::terminate` aufgerufen und das Programm beendet. In C++ kann jeder Typ ausgelöst werden. Es wird jedoch empfohlen, einen Typ auslösen, der direkt oder indirekt von `std::exception` abgeleitet ist. Im vorherigen Beispiel der Ausnahmetyp [Invalid_argument](../standard-library/invalid-argument-class.md), ist in der Standardbibliothek in definiert die [\< Stdexcept>](../standard-library/stdexcept.md) -Headerdatei. C++ kennt und benötigt keinen `finally`-Block, um sicherzustellen, dass alle Ressourcen freigegeben werden, wenn eine Ausnahme ausgelöst wird. Die RAII-Technik (Resource Acquisition Is Initialization, Ressourcenbelegung ist Initialisierung), die intelligente Zeiger verwendet, bietet die erforderliche Funktionalität zur Ressourcenbereinigung. Weitere Informationen finden Sie unter [wie: Entwurf für die Ausnahmesicherheit](../cpp/how-to-design-for-exception-safety.md). Informationen über die C++-stapelentlademechanismus finden Sie unter [Ausnahmen und Stapel entladen](../cpp/exceptions-and-stack-unwinding-in-cpp.md).  
  
## <a name="basic-guidelines"></a>Grundlegende Richtlinien  
 Stabile Fehlerbehandlung ist in jeder Programmiersprache schwierig. Obwohl Ausnahmen etliche Features bereitstellen, die gute Fehlerbehandlung unterstützen, können sie Ihnen nicht die gesamte Arbeit abnehmen. Um die Vorteile des Ausnahmemechanismus auszuschöpfen, sollten Sie Ausnahmen bei der Entwicklung Ihres Codes einplanen.  
  
-   Verwenden Sie Assertionen, um Fehler zu verhindern, die nie auftreten sollten. Verwenden Sie Ausnahmen, um Fehler abzufangen, die beispielsweise bei der Eingabevalidierung oder in Parametern von öffentlichen Funktionen auftreten können. Weitere Informationen finden Sie im Abschnitt **Ausnahmen im Vergleich. Assertionen**.  
  
-   Verwenden Sie Ausnahmen, wenn der Code, der den Fehler behandelt, durch einen oder mehrere eingeschobene Funktionsaufrufe von dem Code getrennt ist, der den Fehler erkennt. Erwägen Sie, Fehlercodes statt leistungskritischer Schleifen zu verwenden, wenn der Code, der den Fehler behandelt, eng mit dem Code gekoppelt ist, der den Fehler erkennt. Weitere Informationen darüber, wann Ausnahmen nicht zu verwenden, finden Sie unter [(NOTINBUILD) bei nicht auf Ausnahmen verwenden](assetId:///e810df8b-2217-4e81-bae5-02f0a69f1346).  
  
-   Für jede Funktion, die eine Ausnahme auslösen oder verteilen kann, sollten Sie eine der drei Ausnahmegarantien bereitstellen: die starke Garantie, die grundlegende Garantie oder die Nothrow (Noexcept)-Garantie. Weitere Informationen finden Sie unter [wie: Entwurf für die Ausnahmesicherheit](../cpp/how-to-design-for-exception-safety.md).  
  
-   Lösen Sie Ausnahmen per Wert aus, fangen Sie Ausnahmen per Referenz ab. Fangen Sie nicht ab, was Sie nicht behandeln können. Weitere Informationen finden Sie unter [(NOTINBUILD) Richtlinien für das Auslösen und Abfangen von Ausnahmen (C++)](assetId:///0a9b0a3a-64c5-43f5-a080-fca69b89e839).  
  
-   Verwenden Sie keine Ausnahmespezifikationen; sie sind seit C++11 veraltet. Weitere Informationen finden Sie im Abschnitt **Ausnahmespezifikationen und Noexcept**.  
  
-   Verwenden Sie wenn möglich Ausnahmetypen der Standardbibliothek. Leiten Sie benutzerdefinierte Ausnahmetypen aus der [Exception-Klasse](../standard-library/exception-class1.md) Hierarchie. Weitere Informationen finden Sie unter [(NOTINBUILD) Gewusst wie: Verwenden Sie die Standard-Bibliothek Ausnahmeobjekte](assetId:///ad1fb785-ed4e-4d94-8e84-964353aed7b6).  
  
-   Lassen Sie Ausnahmen nicht von Destruktoren oder Funktionen zur Speicherfreigabe auslösen.  
  
## <a name="exceptions-and-performance"></a>Ausnahmen und Leistungsfähigkeit  
 Der Ausnahmemechanismus verursacht nur sehr geringe Leistungseinbußen, wenn keine Ausnahme ausgelöst wird. Wenn eine Ausnahme ausgelöst wird, sind die Kosten für Stapeldurchlauf und -Entladung ungefähr mit den Kosten eines Funktionsaufrufs vergleichbar. Zwar sind zusätzliche Datenstrukturen erforderlich, um die Aufrufliste zu durchlaufen, nachdem ein `try`-Block erreicht wurde, und es sind Zusatzbefehle nötig, um den Stapel zu entladen, wenn eine Ausnahme ausgelöst wird. Trotzdem sind in den meisten Szenarien die entsprechenden Leistungseinbußen und der Speicherbedarf nicht signifikant. Die nachteilige Auswirkung von Ausnahmen auf die Leistung ist wahrscheinlich nur auf Systemen mit sehr eingeschränktem Arbeitsspeicher von Bedeutung, oder in leistungskritischen Schleifen, in denen ein Fehler wahrscheinlich wiederkehrend auftritt, und in denen der den Fehler behandelnde Code eng mit dem Code gekoppelt ist, der den Fehler mitteilt. In jedem Fall ist es unmöglich, die Effektivkosten von Ausnahmen ohne Codeprofilierung und Messungen zu ermitteln. Auch in den seltenen Fällen, in denen die Kosten signifikant sind, sollten Sie abwägen, ob diese Kosten nicht die Vorteile rechtfertigen (wie korrekter Code, leichtere Verwaltbarkeit und andere), die von einer gut entworfenen Ausnahmerichtlinie sichergestellt werden.  
  
## <a name="exceptions-vs-assertions"></a>Ausnahmen und Assertionen  
 Ausnahmen und Assertionen sind zwei verschiedene Mechanismen zum Erkennen von Laufzeitfehlern in einem Programm. Verwenden Sie Assertionen, um während der Entwicklung Bedingungen zu ermitteln, die niemals zutreffen dürfen, wenn der gesamte Code fehlerfrei ist. Es gibt keine Möglichkeit, einen solchen Fehler mit einer Ausnahme zu behandeln, weil der Fehler darauf hinweist, dass etwas im Code behoben werden muss. Der Fehler stellt keine Bedingung dar, die das Programm zur Laufzeit beheben muss. Eine Assertion beendet die Ausführung in der Anweisung, damit Sie den Programmzustand im Debugger überprüfen können. Dagegen setzt eine Ausnahme die Programmausführung bis zum ersten entsprechenden catch-Handler fort. Verwenden Sie Ausnahmen, um Fehlerbedingungen zu überprüfen, die zur Laufzeit auftreten können (beispielsweise "Datei nicht gefunden" oder "Nicht genügend Arbeitsspeicher"), auch wenn der Code korrekt ist. Sie sollten die Programmausführung nach solchen Bedingungen nicht sofort beenden, sondern vorher zumindest noch eine entsprechende Meldung in eine Protokolldatei schreiben. Überprüfen Sie immer Argumente für öffentliche Funktionen mithilfe von Ausnahmen. Auch wenn die Funktion fehlerfrei ist, haben Sie möglicherweise keine vollständige Kontrolle über die Argumente, die ein Benutzer übergibt.  
  
## <a name="c-exceptions-versus-windows-seh-exceptions"></a>C++-Ausnahmen und Windows SEH-Ausnahmen  
 Sowohl C-Programme als auch C++-Programme können den Mechanismus der strukturierten Ausnahmebehandlung (Structured Exception Handling, SEH) im Windows-Betriebssystem verwenden. Die Konzepte in SEH entsprechen denen für C++-Ausnahmen, außer dass SEH die Konstrukte `__try`, `__except` und `__finally` anstelle von `try` und `catch` verwendet. In Visual C++ werden C++-Ausnahmen für SEH implementiert. Wenn Sie jedoch C++-Code schreiben, verwenden Sie die Syntax für C++-Ausnahmen.  
  
 Weitere Informationen zu SEH finden Sie unter [strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md).  
  
## <a name="exception-specifications-and-noexcept"></a>Ausnahmespezifikationen und noexcept  
 Ausnahmespezifikationen wurden in C++ als Möglichkeit eingeführt, um die Ausnahmen festzulegen, die eine Funktion auslösen kann. Ausnahmespezifikationen haben sich in der Praxis jedoch als problematisch herausgestellt und wurden im Normenentwurf C++11 als veraltet gekennzeichnet. Es wird empfohlen, Ausnahmespezifikationen nicht zu verwenden, mit Ausnahme von `throw()`, wodurch angegeben wird, dass keine Ausnahmen ausgelöst werden dürfen. Bei Verwendung der Ausnahmespezifikationen des Typs `throw(`*Typ*`)`, beachten Sie, [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] folgt nicht dem Standard auf bestimmte Weise. Weitere Informationen finden Sie unter [Ausnahmespezifikationen (Throw)](../cpp/exception-specifications-throw-cpp.md). Der Bezeichner `noexcept` wird in C++11 als die bevorzugte Alternative zu `throw()` eingeführt.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Schnittstelle zwischen nicht- Ausnahmen Code](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)   
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)