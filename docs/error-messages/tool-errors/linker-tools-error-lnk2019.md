---
title: Linkertoolfehler Lnk2019 | Microsoft-Dokumentation
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
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 86b43f2688b6e1dbfb39dfec681ca9adafd2c093
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2019"></a>Linkertoolfehler LNK2019
nicht aufgelöstes externes Symbol 'symbol' in Funktion 'funktion' referenziert  
  
 Der Linker konnte für das externe Symbol "`symbol`", das in der Funktion "`function`" verwendet wird, keine Definition finden.  
  
 Es gibt viele Probleme, die diesen Fehler verursachen können. Dieses Thema hilft Ihnen dabei, die Ursache zu identifizieren und eine Lösung zu finden.  
  
 Ein *Symbol* ist der Name der Compiler für eine Funktion oder eine globale Variable verwendet. Ein *externes Symbol* ist der Name verwendet, um ein Symbol zu verweisen, die in einer anderen Datei Quelle oder das Objekt definiert ist. Der Linker muss *beheben*, oder suchen Sie die Definition für das externe Symbol für jede Funktion oder eine globale Variable, die durch jede kompilierte Datei verwendet wird, wenn sie in einer Anwendung oder DLL verknüpft ist. Wenn der Linker in keiner der verknüpften Dateien eine entsprechende Definition für ein externes Symbol finden kann, wird LNK2019 generiert.  
  
 Dieser Fehler kann auftreten, wenn die Objekt- oder Bibliotheksdatei mit der Definition eines Symbols nicht im Build enthalten ist. Es kann auch auftreten, wenn der Symbolname vom Linker gesuchte nicht den Namen des Symbols in die Bibliothek oder Objektdatei übereinstimmt, der ihn definiert. Dies kann geschehen, wenn der Name in der aufrufende Code ist falsch geschrieben, Großschreibung verwendet, mithilfe eine andere Aufrufkonvention oder verschiedene Parameter angegeben.  
  
 Code mit C++-Bindung verwendet [Namensergänzung](../../error-messages/tool-errors/name-decoration.md), auch bekannt als *namenszerlegung*, um zusätzliche Informationen über eine Variable oder Funktion und Aufrufkonvention in den Namen eines Symbols zu codieren. Der *ergänzte Name* ist der Name, der vom Linker zum Auflösen externer Symbole gesucht wird. Da die Typinformationen Teil des ergänzten Symbolnamens wird, kann LNK2019 führen, wenn die Deklaration für das externe Symbol, in dem sie verwendet wird, nicht die Deklaration des Symbols entspricht, definiert wird. Damit Sie die Ursache des Fehlers ermitteln können, zeigt die Fehlermeldung sowohl der "Anzeigename" den Namen, die in Quellcode und den ergänzten Namen (in Klammern) für die nicht aufgelöstes externes Symbol verwendet. Sie müssen nicht wissen, wie Sie übersetzen den ergänzten Namen, um es mit anderen ergänzten Namen vergleichen zu können.  
  
 **Häufige Probleme**  
  
 Hier sind einige der häufigsten Probleme aufgeführt, die zum Fehler LNK2019 führen:  
  
-   **Die Objektdatei oder die Bibliothek mit der Definition des Symbols ist nicht verknüpft.** In Visual Studio stellen Sie sicher, dass die Quelldatei mit der Definition erstellt und als Teil des Projekts verknüpft ist. Stellen Sie sicher, dass die Quelldatei mit der Definition kompiliert wird und die sich ergebenden Objektdatei in der Liste der Dateien für eine Verknüpfung enthalten ist, in der Befehlszeile.  
  
-   **Die Deklaration des Symbols ist nicht identisch mit der Definition des Symbols geschrieben.** Überprüfen Sie die richtige Schreibweise und Groß-/Kleinschreibung wird in der Deklaration und Definition verwendet, und wo das Symbol verwendet oder aufgerufen wird.  
  
-   **Eine Funktion wird verwendet, aber die Art und Anzahl der Parameter nicht die Funktionsdefinition überein.** Die Funktionsdeklaration muss mit die Definition übereinstimmen. Stellen Sie sicher, dass der Funktionsaufruf der Deklaration entspricht und dass die Deklaration mit der Definition übereinstimmt. Für Code, der Vorlagenfunktionen aufruft, sind auch entsprechende Deklarationen der Vorlagenfunktionen erforderlich, die dieselben Vorlagenparameter wie die Definition enthalten. Ein Beispiel für eine Vorlage Deklaration Nichtübereinstimmung finden Sie unter LNK2019e.cpp im Abschnitt "Beispiele".  
  
-   **Eine Funktion oder Variable wurde deklariert, aber nicht definiert.** Dies bedeutet normalerweise eine Deklaration, die in einer Headerdatei vorhanden ist, aber keine entsprechende Definition wird implementiert. Für Memberfunktionen oder statische Datenmember muss die Implementierung die Klassenbereichsauswahl enthalten. Ein Beispiel finden Sie unter [fehlender Funktionsrumpf oder fehlende Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md).  
  
-   **Die Aufrufkonvention unterscheidet sich zwischen der Deklaration und Definition der Funktion.** Aufrufkonventionen ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md), oder [__vectorcall](../../cpp/vectorcall.md)) werden als Teil des ergänzten Namens codiert. Stellen Sie sicher, dass die Aufrufkonvention identisch ist.  
  
-   **Ein Symbol ist in einer C#-Datei definiert, aber ohne Verwendung von Extern "C" in einer C++-Datei deklariert.** Symbole, die in einer Datei, die als C kompiliert ist definiert haben andere ergänzte Namen als Symbole, die in einer C++-Datei deklariert werden, es sei denn, Sie verwenden ein [Extern "C"](../../cpp/using-extern-to-specify-linkage.md) Modifizierer. Stellen Sie sicher, dass die Deklaration der Kompilierungsverknüpfung für jedes Symbol entspricht.  
  
     Auch wenn Sie ein Symbol in einer C++-Datei definieren, die von einem C-Programm verwendet wird, verwenden Sie `extern "C"` in der Definition.  
  
-   **Ein Symbol wird als static definiert und später außerhalb der Datei referenziert.** In C++ ist anders als in C [globale Konstanten](../../error-messages/tool-errors/global-constants-in-cpp.md) haben `static` Verknüpfung. Um diese Einschränkung zu umgehen, können Sie die `const` -Initialisierungen in eine Headerdatei einfügen und diesen Header anschließend in die CPP-Dateien einfügen, oder Sie deklarieren die Variable als nicht konstant und verwenden einen konstanten Verweis, um darauf zuzugreifen.  
  
-   **Ein statischer Member einer Klasse ist nicht definiert.** Ein statischer Klassenmember muss eine eindeutige Definition aufweisen, da ansonsten ODR (One Definition Rule) verletzt wird. Ein statischer Klassenmember, der nicht inline definiert werden kann, muss anhand seines vollqualifizierten Namens in einer Quelldatei definiert werden. Wenn er überhaupt nicht definiert wird, generiert der Linker LNK2019.  
  
-   **Eine Buildabhängigkeit wird nur als projektabhängigkeit in der Projektmappe definiert.** In früheren Versionen von [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] war diese Ebene der Abhängigkeit ausreichend. Allerdings beginnend mit Visual Studio 2010, [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] erfordert eine [Projekt-zu-Projekt-Verweis](/visualstudio/ide/managing-references-in-a-project). Wenn Ihr Projekt keinen Interprojektverweis enthält, wird dieser Linkerfehler möglicherweise angezeigt. Fügen Sie einen Interprojektverweis hinzu, um den Fehler zu beheben.  
  
-   **Sie erstellen eine Konsolenanwendung anhand von Einstellungen für eine Windows-Anwendung**. Wenn die Fehlermeldung **unresolved external symbol WinMain referenced in function**`function_name`lautet, verknüpfen Sie über **/SUBSYSTEM:CONSOLE** anstelle von **/SUBSYSTEM:WINDOWS**. Weitere Informationen zu dieser Einstellung und Anweisungen zum Festlegen dieser Eigenschaft in Visual Studio finden Sie unter [/Subsystem (Subsystem angeben)](../../build/reference/subsystem-specify-subsystem.md).  
  
-   **Sie verwenden verschiedene Compileroptionen für Inlinefunktionen in anderen Quelldateien.** Durch die Verwendung von Inlinefunktionen, die in CPP-Dateien definiert sind, und die Kombination von Inlinecompileroptionen für Funktionen in anderen Quelldateien kann LNK2019 verursacht werden. Weitere Informationen finden Sie unter [Probleme bei Inlinefunktionen](../../error-messages/tool-errors/function-inlining-problems.md).  
  
-   **Sie verwenden automatische Variablen außerhalb ihres Bereichs.** Automatische Variablen (mit Funktionsgültigkeitsbereich) können nur im Rahmen dieser Funktion verwendet werden. Diese Variablen können nicht `extern` deklariert und in anderen Quelldateien verwendet werden. Ein Beispiel finden Sie unter [automatische (mit Funktionsgültigkeitsbereich) Variablen](../../error-messages/tool-errors/automatic-function-scope-variables.md).  
  
-   **Sie rufen intrinsische Funktionen oder übergeben Argumenttypen an intrinsische Funktionen, die auf der Zielarchitektur nicht unterstützt werden.** Beispielsweise, wenn Sie eine intrinsische avx2-Funktion, aber geben Sie nicht die [/arch: avx2](../../build/reference/arch-x86.md) (Compileroption), nimmt der Compiler an, dass die systeminterne Funktion eine externe Funktion handelt. Anstelle einer Inlineanweisung generiert der Compiler einen Aufruf an ein externes Symbol mit demselben Namen wie die intrinsische Funktion. Wenn der Linker versucht, die Definition dieser fehlende Funktion zu finden, wird LNK2019 generiert. Stellen Sie sicher, dass Sie nur intrinsische Funktionen und Typen verwenden, die von der Zielarchitektur unterstützt werden.  
  
-   **Sie kombinieren Code mit dem systemeigenen Wchar_t mit Code verwendet, die nicht.** Durch die in Visual C++ 2005 vorgenommene Konformitätsverbesserung der C++-Sprache wurde `wchar_t` standardmäßig als systemeigener Typ festgelegt. Verwenden Sie die [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Compileroption zum Generieren von Code mit Bibliotheks- und Objektnamen-Dateien, die mit früheren Versionen von Visual C++ kompiliert kompatibel. Wenn nicht alle Dateien mit denselben **/Zc:wchar_t** -Einstellungen kompiliert wurden, werden Typenverweise möglicherweise nicht in kompatible Typen aufgelöst. Überprüfen Sie, ob `wchar_t` -Typen in allen Bibliotheks- und Objektdateien kompatibel sind. Aktualisieren Sie hierzu entweder die verwendeten Typen, oder verwenden Sie beim Kompilieren konsistente **/Zc:wchar_t** -Einstellungen.  
  
 Weitere Informationen zu möglichen Ursachen und Lösungen für LNK2019 finden Sie in der Stack Overflow-Frage [What is an undefined reference/unresolved external symbol error and how do I fix it?](http://stackoverflow.com/q/12573816/2002113).  
  
 **Diagnosetools**  
  
 Es kann schwierig sein festzustellen, warum der Linker eine bestimmte Symboldefinition nicht finden kann. Häufig besteht das Problem darin, dass Sie den Code nicht in Ihren Build einbezogen haben oder dass durch Buildoptionen andere ergänzte Namen für externe Symbole erstellt wurden. Es gibt mehrere Tools und Optionen, mit denen Sie einen Fehler LNK2019 diagnostizieren können.  
  
-   Die [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) (Linkeroption) können Sie bestimmen, welche Dateien der Linker verweist. Damit können Sie überprüfen, ob die Datei mit der Definition des Symbols in Ihrem Build enthalten ist.  
  
-   Die [/EXPORTS](../../build/reference/dash-exports.md) und [/SYMBOLS](../../build/reference/symbols.md) Optionen des DUMPBIN-Hilfsprogramms können Sie ermitteln, welche Symbole in den DLL- und Objekt- oder Bibliotheksdateien definiert sind. Stellen Sie sicher, dass die exportierten ergänzten Namen den ergänzten Namen entsprechen, die vom Linker gesucht werden.  
  
-   Das Hilfsprogramm UNDNAME kann Ihnen das entsprechende nicht ergänzte externe Symbol für einen ergänzten Namen anzeigen.  
  
 **Beispiele**  
  
 Hier sind einige Beispiele für Code aufgeführt, der einen Fehler LNK2019 verursacht, sowie Informationen zur Behebung des Fehlers.  
  
 **Ein Symbol wurde deklariert, aber nicht definiert**  
  
 Im folgenden Beispiel wird LNK2019 generiert, da ein externes Symbol deklariert, aber nicht definiert wurde:  
  
```cpp  
// LNK2019.cpp  
// Compile by using: cl /EHsc LNK2019.cpp  
// LNK2019 expected  
extern char B[100];   // B is not available to the linker  
int main() {  
   B[0] = ' ';   // LNK2019  
}  
```  
  
 Hier sehen Sie ein weiteres Beispiel:  
  
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
  
 Wenn `i` und `g` nicht in einer der Dateien im Build definiert wurden, generiert der Linker LNK2019. Sie können die Fehler beheben, indem Sie die Quellcodedatei mit den Definitionen in die Kompilierung einbeziehen. Alternativ können Sie OBJ- oder LIB-Dateien, die die Definitionen enthalten, an den Linker übergeben.  
  
 **Ein statischer Datenmember deklariert, aber nicht definiert.**  
  
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
  
 **Deklarationsparameter stimmen nicht mit Definition überein.**  
  
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
  
 **Inkonsistente Wchar_t-Typdefinitionen**  
  
 Im folgenden Beispiel wird eine DLL mit einem Export erstellt, der einen `WCHAR`verwendet, der in `wchar_t`aufgelöst wird.  
  
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
  
 Um diesen Fehler zu beheben, ändern Sie `unsigned short` auf `wchar_t` oder `WCHAR`, oder Kompilieren Sie "LNK2019g.cpp" mit **/Zc:wchar_t-**.
