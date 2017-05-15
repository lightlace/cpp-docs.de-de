---
title: Linkertoolfehler Lnk2019 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2019
dev_langs:
- C++
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.assetid: 4392be92-195c-4eb2-bd4d-49cfac3ca291
caps.latest.revision: 39
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: fad921c3b4f13f5704c293188c0b91315146c33c
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="linker-tools-error-lnk2019"></a>Linkertoolfehler LNK2019
nicht aufgelöstes externes Symbol '*Symbol*"verwiesen wird, in der Funktion"*Funktion*"  
  
Den kompilierten Code für *Funktion* wird ein Verweis oder ein Aufruf von *Symbol*, allerdings Symbol befindet sich nicht in einer der an den Linker festgelegten Objektdateien oder Bibliotheken definiert.  
  
Diese Fehlermeldung wird gefolgt von Schwerwiegender Fehler [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). Sie müssen alle LNK2001 und LNK2019 Fehler zum Beheben von Fehler LNK1120 beheben.  
  
## <a name="possible-causes"></a>Mögliche Ursachen  
  
Es gibt viele Möglichkeiten, diesen Fehler zu erhalten, aber alle umfassen einen Verweis auf eine Funktion oder Variable, die nicht vom Linker *beheben*, oder suchen Sie eine Definition für. Der Compiler erkennen, wenn ein Symbol, das nicht *deklariert*, aber nicht wenn kein *definiert*, da die Definition in einer anderen Quelldatei oder Bibliothek sein kann. Wenn ein Symbol bezeichnet, aber nie definiert, generiert der Linker einen nicht aufgelöstes externes Symbol-Fehler.  
  
Hier sind einige der häufigsten Probleme aufgeführt, die zum Fehler LNK2019 führen:  
  
-   **Die Objektdatei oder Bibliothek, die die Definition des Symbols enthält, ist nicht verknüpft.** In Visual Studio stellen Sie sicher, dass die Quelldatei mit der Definition erstellt und als Teil Ihres Projekts verknüpft wird. Stellen Sie sicher, dass die Quelldatei mit der Definition kompiliert wird, und dass die resultierende Objektdatei in der Liste der Dateien für eine Verknüpfung enthalten ist, in der Befehlszeile.  
  
-   **Die Schreibweise der Symboldeklaration stimmt nicht mit der Definition des Symbols überein.** Überprüfen Sie die richtige Schreibweise und Groß-/Kleinschreibung in der Deklaration und Definition verwendet wird und immer, wenn das Symbol verwendet oder aufgerufen.  
  
-   **Eine Funktion wird verwendet, aber der Typ oder die Anzahl der Parameter stimmen nicht mit der Funktionsdefinition überein.** Die Funktionsdeklaration muss mit die Definition übereinstimmen. Stellen Sie sicher, dass der Funktionsaufruf der Deklaration entspricht und dass die Deklaration mit der Definition übereinstimmt. Für Code, der Vorlagenfunktionen aufruft, sind auch entsprechende Deklarationen der Vorlagenfunktionen erforderlich, die dieselben Vorlagenparameter wie die Definition enthalten. Ein Beispiel für eine Vorlage Deklaration Nichtübereinstimmung finden Sie unter Beispiel LNK2019e.cpp im Abschnitt "Beispiele".  
  
-   **Eine Funktion oder Variable wurde deklariert, aber nicht definiert.** Dies bedeutet normalerweise eine Deklaration, die in einer Headerdatei vorhanden ist, aber keine entsprechende Definition implementiert wurde. Für Memberfunktionen oder statische Datenmember muss die Implementierung die Klassenbereichsauswahl enthalten. Ein Beispiel finden Sie unter [Missing Function Body or Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md).  
  
-   **Die Aufrufkonvention unterscheidet sich zwischen der Deklaration und der Definition der Funktion.** Aufrufkonventionen ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md)oder [__vectorcall](../../cpp/vectorcall.md)) werden als Teil des ergänzten Namens codiert. Stellen Sie sicher, dass die Aufrufkonvention identisch ist.  
  
-   **Ein Symbol ist in einer C-Datei definiert, wurde aber ohne Verwendung von extern "C" in einer C++-Datei deklariert.** Symbole, die in einer in C kompilierten Datei definiert sind, besitzen andere ergänzte Namen als Symbole, die in einer C++-Datei deklariert werden, es sei denn, Sie verwenden einen [extern "C"](../../cpp/using-extern-to-specify-linkage.md) -Modifizierer. Stellen Sie sicher, dass die Deklaration der Kompilierungsverknüpfung für jedes Symbol entspricht. Auch wenn Sie ein Symbol in einer C++-Datei definieren, die von einem C-Programm verwendet wird, verwenden Sie `extern "C"` in der Definition.  
  
-   **Ein Symbol wird als "static" definiert und später außerhalb der Datei referenziert.** Anders als in C, verfügen [globale Konstanten](../../error-messages/tool-errors/global-constants-in-cpp.md) in C++ über eine `static` -Verknüpfung. Um diese Einschränkung zu umgehen, können Sie die `const` -Initialisierungen in eine Headerdatei einfügen und diesen Header anschließend in die CPP-Dateien einfügen, oder Sie deklarieren die Variable als nicht konstant und verwenden einen konstanten Verweis, um darauf zuzugreifen.  
  
-   **Ein statischer Member einer Klasse wurde nicht definiert.** Ein statischer Klassenmember muss eine eindeutige Definition aufweisen, da ansonsten ODR (One Definition Rule) verletzt wird. Ein statischer Klassenmember, der nicht inline definiert werden kann, muss anhand seines vollqualifizierten Namens in einer Quelldatei definiert werden. Wenn er überhaupt nicht definiert wird, generiert der Linker LNK2019.  
  
-   **Eine Buildabhängigkeit wird in der Projektmappe nur als Projektabhängigkeit definiert.** In früheren Versionen von Visual Studio war diese Ebene der Abhängigkeit ausreichend. Beginnend mit Visual Studio 2010, Visual Studio erfordert jedoch eine [Projekt-zu-Projekt-Verweises](/visualstudio/ide/managing-references-in-a-project). Wenn Ihr Projekt keinen Interprojektverweis enthält, wird dieser Linkerfehler möglicherweise angezeigt. Fügen Sie einen Interprojektverweis hinzu, um den Fehler zu beheben.  
  
-   **Sie erstellen eine Konsolenanwendung anhand von Einstellungen für eine Windows-Anwendung**. Wenn die Fehlermeldung **unresolved external symbol WinMain referenced in function**`function_name`lautet, verknüpfen Sie über **/SUBSYSTEM:CONSOLE** anstelle von **/SUBSYSTEM:WINDOWS**. Weitere Informationen zu dieser Einstellung und Anweisungen zum Festlegen dieser Eigenschaft in Visual Studio finden Sie unter [/SUBSYSTEM (Specify Subsystem)](../../build/reference/subsystem-specify-subsystem.md).  
  
-   **Sie verwenden verschiedene Compileroptionen für Inlinefunktionen in anderen Quelldateien.** Durch die Verwendung von Inlinefunktionen, die in CPP-Dateien definiert sind, und die Kombination von Inlinecompileroptionen für Funktionen in anderen Quelldateien kann LNK2019 verursacht werden. Weitere Informationen finden Sie unter [Function Inlining Problems](../../error-messages/tool-errors/function-inlining-problems.md).  
  
-   **Sie verwenden automatische Variablen außerhalb ihres Bereichs.** Automatische Variablen (mit Funktionsgültigkeitsbereich) können nur im Rahmen dieser Funktion verwendet werden. Diese Variablen können nicht `extern` deklariert und in anderen Quelldateien verwendet werden. Ein Beispiel finden Sie unter [Automatic (Function Scope) Variables](../../error-messages/tool-errors/automatic-function-scope-variables.md).  
  
-   **Sie rufen intrinsische Funktionen auf oder übergeben Argumenttypen an intrinsische Funktionen, die auf der Zielarchitektur nicht unterstützt werden.** Wenn Sie beispielsweise eine intrinsische AVX2-Funktion verwenden, aber nicht die Compileroption [/ARCH:AVX2](../../build/reference/arch-x86.md) angeben, nimmt der Compiler an, dass es sich bei der intrinsischen um eine externe Funktion handelt. Anstelle einer Inlineanweisung generiert der Compiler einen Aufruf an ein externes Symbol mit demselben Namen wie die intrinsische Funktion. Wenn der Linker versucht, die Definition dieser fehlende Funktion zu finden, wird LNK2019 generiert. Stellen Sie sicher, dass Sie nur intrinsische Funktionen und Typen verwenden, die von der Zielarchitektur unterstützt werden.  
  
-   **Sie kombinieren Code mit dem systemeigenen Wchar verwendet\_t mit Code, der nicht.** Durch die in Visual C++ 2005 vorgenommene Konformitätsverbesserung der C++-Sprache wurde `wchar_t` standardmäßig als systemeigener Typ festgelegt. Sie müssen die Compileroption [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) verwenden, um Code zu generieren, der mit Bibliotheks- und Objektdateien kompatibel ist, die mit früheren Versionen von Visual C++ kompiliert wurden. Wenn nicht alle Dateien unter Verwendung des gleichen kompiliert wurden **/Zc:wchar\_t** Einstellungen Typenverweise möglicherweise nicht in kompatible Typen aufgelöst. Überprüfen Sie, ob `wchar_t` -Typen in allen Bibliotheks- und Objektdateien kompatibel sind. Aktualisieren Sie hierzu entweder die verwendeten Typen, oder verwenden Sie beim Kompilieren konsistente **/Zc:wchar_t** -Einstellungen.  
  
## <a name="diagnosis-tools"></a>Diagnosetools    
  
Es kann schwierig sein festzustellen, warum der Linker eine bestimmte Symboldefinition nicht finden kann. Häufig ist das Problem, dass Sie nicht den Code mit der Definition in Ihren Build einbezogen haben oder Build erstellten Optionen andere Namen für externe Symbole ergänzte. Es gibt mehrere Tools und Optionen, mit denen Sie einen Fehler LNK2019 diagnostizieren können.  
  
-   Mithilfe der Linkeroption [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) können Sie ermitteln, auf welche Dateien der Linker verweist. Damit können Sie überprüfen, ob die Datei mit der Definition des Symbols in Ihrem Build enthalten ist.  
  
-   Anhand der Optionen [/EXPORTS](../../build/reference/dash-exports.md) und [/SYMBOLS](../../build/reference/symbols.md) des DUMPBIN-Hilfsprogramms können Sie ermitteln, welche Symbole in den DLL- und Objekt- oder Bibliotheksdateien definiert sind. Stellen Sie sicher, dass die exportierten ergänzten Namen den ergänzten Namen entsprechen, die vom Linker gesucht werden.  
  
-   Das Hilfsprogramm UNDNAME kann Ihnen das entsprechende nicht ergänzte externe Symbol für einen ergänzten Namen anzeigen.  
## <a name="examples"></a>Beispiele  
  
Hier sind einige Beispiele für Code aufgeführt, der einen Fehler LNK2019 verursacht, sowie Informationen zur Behebung des Fehlers.  
  
### <a name="a-symbol-is-declared-but-not-defined"></a>Ein Symbol wurde deklariert, aber nicht definiert  
  
In diesem Beispiel wird eine externe Variable deklariert, aber nicht definiert:  
  
```cpp  
// LNK2019.cpp  
// Compile by using: cl /EHsc /W4 LNK2019.cpp  
// LNK2019 expected  
extern char B[100];   // B is not available to the linker  
int main() {  
   B[0] = ' ';   // LNK2019  
}  
```  
  
Hier ist ein weiteres Beispiel, in dem eine Variable und die Funktion als deklariert `extern` jedoch keine Definition bereitgestellt wird:  
  
```cpp  
// LNK2019c.cpp  
// Compile by using: cl /EHsc LNK2019c.cpp  
// LNK2019 expected  
extern int i;  
extern void g();  
void f() {  
   i++;  
   g();  
}  
int main() {}  
```  
  
Es sei denn, `i` und `g` definiert sind in einer der Dateien im Build enthaltenes, generiert der Linker LNK2019. Sie können die Fehler beheben, indem Sie die Quellcodedatei mit den Definitionen in die Kompilierung einbeziehen. Alternativ können Sie OBJ- oder LIB-Dateien, die die Definitionen für den Linker übergeben.  
  
### <a name="a-static-data-member-is-declared-but-not-defined"></a>Ein statischer Datenmember wurde deklariert, aber nicht definiert  
  
LNK2019 kann auch auftreten, wenn ein statischer Datenmember deklariert, aber nicht definiert wurde. Im folgenden Beispiel wird LNK2019 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```cpp  
// LNK2019b.cpp  
// Compile by using: cl /EHsc LNK2019b.cpp  
// LNK2019 expected  
struct C {  
   static int s;  
};  
  
// Uncomment the following line to fix the error.  
// int C::s;  
  
int main() {  
   C c;  
   C::s = 1;  
}  
```  
  
### <a name="declaration-parameters-do-not-match-definition"></a>Deklarationsparameter stimmen nicht mit Definition überein  
  
Code, der Vorlagenfunktionen aufruft, muss übereinstimmende Deklarationen von Vorlagenfunktionen aufweisen. Deklarationen müssen dieselben Vorlagenparameter wie die Definition enthalten. Das folgende Beispiel generiert LNK2019 für einen benutzerdefinierten Operator und zeigt, wie Sie diesen Fehler beheben.  
  
```cpp  
// LNK2019e.cpp  
// compile by using: cl /EHsc LNK2019e.cpp  
// LNK2019 expected  
#include <iostream>  
using namespace std;  
  
template<class T> class   
Test {  
   // The operator<< declaration does not match the definition below:  
   friend ostream& operator<<(ostream&, Test&);  
   // To fix, replace the line above with the following:  
   // template<typename T> friend ostream& operator<<(ostream&, Test<T>&);  
};  
  
template<typename T>  
ostream& operator<<(ostream& os, Test<T>& tt) {  
   return os;  
}  
  
int main() {  
   Test<int> t;  
   cout << "Test: " << t << endl;   // LNK2019 unresolved external  
}  
```  
  
### <a name="inconsistent-wchart-type-definitions"></a>Inkonsistente wchar_t-Typdefinitionen  
  
Dieses Beispiel erstellt eine DLL, die einen Export verfügt, verwendet `WCHAR`, dieser wird in aufgelöst `wchar_t`.  
  
```cpp  
// LNK2019g.cpp  
// compile with: cl /EHsc /LD LNK2019g.cpp  
#include "windows.h"  
// WCHAR resolves to wchar_t  
__declspec(dllexport) void func(WCHAR*) {}  
```  
  
Im folgenden Beispiel wird die DLL im vorherigen Beispiel verwendet und LNK2019 generiert, da die Typen ohne, Short * und WCHAR Vorzeichen\* stimmen nicht überein.  
  
```cpp  
// LNK2019h.cpp  
// compile by using: cl /EHsc LNK2019h LNK2019g.lib  
// LNK2019 expected  
__declspec(dllimport) void func(unsigned short*);  
  
int main() {  
   func(0);  
}  
```  
  
 Ändern Sie zum Beheben dieses Fehlers `unsigned short` auf `wchar_t` oder `WCHAR`, oder Kompilieren Sie "LNK2019g.cpp" über **/Zc:wchar_t-**.  
  
## <a name="additional-resources"></a>Zusätzliche Ressourcen  
  
Weitere Informationen zu möglichen Ursachen und Lösungen für LNK2001, finden Sie unter der Stack Overflow-Frage [Was ist ein nicht definierten Verweis/ein nicht aufgelöstes externes Symbol Fehler und wie behebe ich das Problem?](http://stackoverflow.com/q/12573816/2002113).  


