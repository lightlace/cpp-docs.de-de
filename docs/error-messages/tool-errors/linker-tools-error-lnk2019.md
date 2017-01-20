---
title: "Linkertoolfehler LNK2019"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_check_commonlanguageruntime_version"
  - "LNK2019"
  - "nochkclr.obj"
ms.assetid: 4392be92-195c-4eb2-bd4d-49cfac3ca291
caps.latest.revision: 39
caps.handback.revision: "37"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

nicht aufgelöstes externes Symbol 'symbol' in Funktion 'funktion' referenziert  
  
 Der Linker konnte für das externe Symbol "`symbol`", das in der Funktion "`function`" verwendet wird, keine Definition finden. Es gibt viele Probleme, die diesen Fehler verursachen können. Dieses Thema hilft Ihnen dabei, die Ursache zu identifizieren und eine Lösung zu finden.  
  
 Ein *externes Symbol* ist der deklarierte Name, mit dem Sie im Quellcode auf ein Element verweisen, das in einer anderen Objekt\- oder Bibliotheksdatei definiert ist, z. B. eine externe Funktion oder eine globale Variable. Der Linker ist für die Auflösung aller externen Symbolverweise in den einzelnen Objektdateien zuständig, wenn diese in einer Anwendung oder DLL verknüpft sind. Wenn der Linker in keiner der verknüpften Dateien eine entsprechende Definition für ein externes Symbol finden kann, wird LNK2019 generiert. Dieser Fehler kann auftreten, wenn der Quellcode oder die Bibliotheksdatei mit der Definition des Symbols nicht im Build enthalten ist. Er kann außerdem dann auftreten, wenn der vom Linker gesuchte Name nicht mit dem Namen des Symbols in der Bibliothek oder Objektdatei übereinstimmt, in der das Symbol definiert ist.  
  
 Code mit C\+\+\-Bindung verwendet [Namensergänzung](../../error-messages/tool-errors/name-decoration.md), auch bekannt als *Name\-Mangling*, um zusammen mit dem Symbolnamen zusätzliche Informationen über den Typ und die Aufrufkonvention eines Symbols zu codieren. Der *ergänzte Name* ist der Name, der vom Linker zum Auflösen externer Symbole gesucht wird. Da der Deklarationstyp des Symbolverweises Teil des ergänzten Symbolnamens wird, wird der Fehler LNK2019 möglicherweise verursacht, wenn dieser Deklarationstyp nicht mit dem Deklarationstyp der Symboldefinition übereinstimmt. In der Fehlermeldung werden sowohl das externe Symbol als auch der ergänzte Name angezeigt, damit Sie die Ursache des Fehlers ermitteln können.  
  
 **Häufig auftretende Probleme**  
  
 Hier sind einige der häufigsten Probleme aufgeführt, die zum Fehler LNK2019 führen:  
  
-   **Die Schreibweise der Symboldeklaration stimmt nicht mit der Definition des Symbols überein.** Stellen Sie sicher, dass die richtige Schreibweise verwendet wurde.  
  
-   **Eine Funktion wird verwendet, aber der Typ oder die Anzahl der Parameter stimmen nicht mit der Funktionsdefinition überein.** Die Funktionsdeklaration muss mit die Definition übereinstimmen. Für Code, der Vorlagenfunktionen aufruft, sind auch entsprechende Deklarationen der Vorlagenfunktionen erforderlich, die dieselben Vorlagenparameter wie die Definition enthalten. Stellen Sie sicher, dass der Funktionsaufruf der Deklaration entspricht und dass die Deklaration mit der Definition übereinstimmt.  
  
-   **Eine Funktion oder Variable wurde deklariert, aber nicht definiert.** Dies bedeutet für gewöhnlich, dass in der Headerdatei eine Deklaration vorhanden ist, jedoch keine Definition implementiert wurde. Für Memberfunktionen oder statische Datenmember muss die Implementierung die Klassenbereichsauswahl enthalten. Ein Beispiel finden Sie unter [Fehlender Funktionsrumpf oder fehlende Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md).  
  
-   **Die Aufrufkonvention unterscheidet sich zwischen der Deklaration und der Definition der Funktion.** Aufrufkonventionen \([\_\_cdecl](../../cpp/cdecl.md), [\_\_stdcall](../../cpp/stdcall.md), [\_\_fastcall](../../cpp/fastcall.md) oder [\_\_vectorcall](../../cpp/vectorcall.md)\) werden als Teil des ergänzten Namens codiert. Stellen Sie sicher, dass die Aufrufkonvention identisch ist.  
  
-   **Ein Symbol ist in einer C\-Datei definiert, wurde aber ohne Verwendung von extern "C" in einer C\+\+\-Datei deklariert.** Symbole, die in einer in C kompilierten Datei definiert sind, besitzen andere ergänzte Namen als Symbole, die in einer C\+\+\-Datei deklariert werden, es sei denn, Sie verwenden einen [extern "C"](../../cpp/using-extern-to-specify-linkage.md)\-Modifizierer. Stellen Sie sicher, dass die Deklaration der Kompilierungsverknüpfung für jedes Symbol entspricht.  
  
     Auch wenn Sie ein Symbol in einer C\+\+\-Datei definieren, die von einem C\-Programm verwendet wird, verwenden Sie `extern "C"` in der Definition.  
  
-   **Ein Symbol wird als "static" definiert und später außerhalb der Datei referenziert.** Anders als in C, verfügen [globale Konstanten](../../error-messages/tool-errors/global-constants-in-cpp.md) in C\+\+ über eine `static`\-Verknüpfung. Um diese Einschränkung zu umgehen, können Sie die `const`\-Initialisierungen in eine Headerdatei einfügen und diesen Header anschließend in die CPP\-Dateien einfügen, oder Sie deklarieren die Variable als nicht konstant und verwenden einen konstanten Verweis, um darauf zuzugreifen.  
  
-   **Ein statischer Member einer Klasse wurde nicht definiert.** Ein statischer Klassenmember muss eine eindeutige Definition aufweisen, da ansonsten ODR \(One Definition Rule\) verletzt wird. Ein statischer Klassenmember, der nicht inline definiert werden kann, muss anhand seines vollqualifizierten Namens in einer Quelldatei definiert werden. Wenn er überhaupt nicht definiert wird, generiert der Linker LNK2019.  
  
-   **Eine Buildabhängigkeit wird in der Projektmappe nur als Projektabhängigkeit definiert.** In früheren Versionen von [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] war diese Ebene der Abhängigkeit ausreichend. Ab Visual Studio 2010 erfordert [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] jedoch einen [Interprojektverweis](../Topic/Managing%20references%20in%20a%20project.md). Wenn Ihr Projekt keinen Interprojektverweis enthält, wird dieser Linkerfehler möglicherweise angezeigt. Fügen Sie einen Interprojektverweis hinzu, um den Fehler zu beheben.  
  
-   **Sie erstellen eine Konsolenanwendung anhand von Einstellungen für eine Windows\-Anwendung**. Wenn die Fehlermeldung **unresolved external symbol WinMain referenced in function** `function_name` lautet, verknüpfen Sie über **\/SUBSYSTEM:CONSOLE** anstelle von **\/SUBSYSTEM:WINDOWS**. Weitere Informationen zu dieser Einstellung und Anweisungen zum Festlegen dieser Eigenschaft in Visual Studio finden Sie unter [\/SUBSYSTEM \(Subsystem angeben\)](../../build/reference/subsystem-specify-subsystem.md).  
  
-   **Sie verwenden verschiedene Compileroptionen für Inlinefunktionen in anderen Quelldateien.** Durch die Verwendung von Inlinefunktionen, die in CPP\-Dateien definiert sind, und die Kombination von Inlinecompileroptionen für Funktionen in anderen Quelldateien kann LNK2019 verursacht werden. Weitere Informationen finden Sie unter [Probleme bei Inlinefunktionen](../../error-messages/tool-errors/function-inlining-problems.md).  
  
-   **Sie verwenden automatische Variablen außerhalb ihres Bereichs.** Automatische Variablen \(mit Funktionsgültigkeitsbereich\) können nur im Rahmen dieser Funktion verwendet werden. Diese Variablen können nicht `extern` deklariert und in anderen Quelldateien verwendet werden. Ein Beispiel finden Sie unter [Automatische Variablen \(mit Funktionsgültigkeitsbereich\)](../../error-messages/tool-errors/automatic-function-scope-variables.md).  
  
-   **Sie rufen intrinsische Funktionen auf oder übergeben Argumenttypen an intrinsische Funktionen, die auf der Zielarchitektur nicht unterstützt werden.** Wenn Sie beispielsweise eine intrinsische AVX2\-Funktion verwenden, aber nicht die Compileroption [\/ARCH:AVX2](../../build/reference/arch-x86.md) angeben, nimmt der Compiler an, dass es sich bei der intrinsischen um eine externe Funktion handelt. Anstelle einer Inlineanweisung generiert der Compiler einen Aufruf an ein externes Symbol mit demselben Namen wie die intrinsische Funktion. Wenn der Linker versucht, die Definition dieser fehlende Funktion zu finden, wird LNK2019 generiert. Stellen Sie sicher, dass Sie nur intrinsische Funktionen und Typen verwenden, die von der Zielarchitektur unterstützt werden.  
  
-   **Sie kombinieren Code mit dem systemeigenen Datentyp "wchar\_t" mit Code, der diesen Datentyp nicht verwendet.** Durch die in Visual C\+\+ 2005 vorgenommene Konformitätsverbesserung der C\+\+\-Sprache wurde `wchar_t` standardmäßig als systemeigener Typ festgelegt. Sie müssen die Compileroption [\/Zc:wchar\_t\-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) verwenden, um Code zu generieren, der mit Bibliotheks\- und Objektdateien kompatibel ist, die mit früheren Versionen von Visual C\+\+ kompiliert wurden. Wenn nicht alle Dateien mit denselben **\/Zc:wchar\_t**\-Einstellungen kompiliert wurden, werden Typenverweise möglicherweise nicht in kompatible Typen aufgelöst. Überprüfen Sie, ob `wchar_t`\-Typen in allen Bibliotheks\- und Objektdateien kompatibel sind. Aktualisieren Sie hierzu entweder die verwendeten Typen, oder verwenden Sie beim Kompilieren konsistente **\/Zc:wchar\_t**\-Einstellungen.  
  
 Weitere Informationen zu möglichen Ursachen und Lösungen für LNK2019 finden Sie in der Stack Overflow\-Frage [What is an undefined reference\/unresolved external symbol error and how do I fix it?](http://stackoverflow.com/q/12573816/2002113).  
  
 **Diagnosetools**  
  
 Es kann schwierig sein festzustellen, warum der Linker eine bestimmte Symboldefinition nicht finden kann. Häufig besteht das Problem darin, dass Sie den Code nicht in Ihren Build einbezogen haben oder dass durch Buildoptionen andere ergänzte Namen für externe Symbole erstellt wurden. Es gibt mehrere Tools und Optionen, mit denen Sie einen Fehler LNK2019 diagnostizieren können.  
  
-   Mithilfe der Linkeroption [\/VERBOSE](../../build/reference/verbose-print-progress-messages.md) können Sie ermitteln, auf welche Dateien der Linker verweist. Damit können Sie überprüfen, ob die Datei mit der Definition des Symbols in Ihrem Build enthalten ist.  
  
-   Anhand der Optionen [\/EXPORTS](../../build/reference/dash-exports.md) und [\/SYMBOLS](../../build/reference/symbols.md) des DUMPBIN\-Hilfsprogramms können Sie ermitteln, welche Symbole in den DLL\- und Objekt\- oder Bibliotheksdateien definiert sind. Stellen Sie sicher, dass die exportierten ergänzten Namen den ergänzten Namen entsprechen, die vom Linker gesucht werden.  
  
-   Das Hilfsprogramm UNDNAME kann Ihnen das entsprechende nicht ergänzte externe Symbol für einen ergänzten Namen anzeigen.  
  
 **Beispiele**  
  
 Hier sind einige Beispiele für Code aufgeführt, der einen Fehler LNK2019 verursacht, sowie Informationen zur Behebung des Fehlers.  
  
 **Ein Symbol wurde deklariert, aber nicht definiert**  
  
 Im folgenden Beispiel wird LNK2019 generiert, da ein externes Symbol deklariert, aber nicht definiert wurde:  
  
```cpp  
// LNK2019.cpp // Compile by using: cl /EHsc LNK2019.cpp // LNK2019 expected extern char B[100];   // B is not available to the linker int main() { B[0] = ' ';   // LNK2019 }  
```  
  
 Hier sehen Sie ein weiteres Beispiel:  
  
```cpp  
// LNK2019c.cpp // Compile by using: cl /EHsc LNK2019c.cpp // LNK2019 expected extern int i; extern void g(); void f() { i++; g(); } int main() {}  
```  
  
 Wenn `i` und `g` nicht in einer der Dateien im Build definiert wurden, generiert der Linker LNK2019. Sie können die Fehler beheben, indem Sie die Quellcodedatei mit den Definitionen in die Kompilierung einbeziehen. Alternativ können Sie OBJ\- oder LIB\-Dateien, die die Definitionen enthalten, an den Linker übergeben.  
  
 **Ein statischer Datenmember wurde deklariert, aber nicht definiert**  
  
 LNK2019 kann auch auftreten, wenn ein statischer Datenmember deklariert, aber nicht definiert wurde. Im folgenden Beispiel wird LNK2019 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```cpp  
// LNK2019b.cpp // Compile by using: cl /EHsc LNK2019b.cpp // LNK2019 expected struct C { static int s; }; // Uncomment the following line to fix the error. // int C::s; int main() { C c; C::s = 1; }  
```  
  
 **Deklarationsparameter stimmen nicht mit Definition überein**  
  
 Code, der Vorlagenfunktionen aufruft, muss übereinstimmende Deklarationen von Vorlagenfunktionen aufweisen. Deklarationen müssen dieselben Vorlagenparameter wie die Definition enthalten. Das folgende Beispiel generiert LNK2019 für einen benutzerdefinierten Operator und zeigt, wie Sie diesen Fehler beheben.  
  
```cpp  
// LNK2019e.cpp // compile by using: cl /EHsc LNK2019e.cpp // LNK2019 expected #include <iostream> using namespace std; template<class T> class Test { // The operator<< declaration does not match the definition below: friend ostream& operator<<(ostream&, Test&); // To fix, replace the line above with the following: // template<typename T> friend ostream& operator<<(ostream&, Test<T>&); }; template<typename T> ostream& operator<<(ostream& os, Test<T>& tt) { return os; } int main() { Test<int> t; cout << "Test: " << t << endl;   // LNK2019 unresolved external }  
```  
  
 **Inkonsistente wchar\_t\-Typdefinitionen**  
  
 Im folgenden Beispiel wird eine DLL mit einem Export erstellt, der einen `WCHAR` verwendet, der in `wchar_t` aufgelöst wird.  
  
```cpp  
// LNK2019g.cpp // compile with: cl /EHsc /LD LNK2019g.cpp #include "windows.h" // WCHAR resolves to wchar_t __declspec(dllexport) void func(WCHAR*) {}  
```  
  
 Im folgenden Beispiel wird die DLL aus dem vorherigen Beispiel verwendet und LNK2019 generiert, da die Typen "unsigned short\*" und "WCHAR\*" nicht identisch sind.  
  
```cpp  
// LNK2019h.cpp // compile by using: cl /EHsc LNK2019h LNK2019g.lib // LNK2019 expected __declspec(dllimport) void func(unsigned short*); int main() { func(0); }  
```  
  
 Um diesen Fehler zu beheben, ändern Sie `unsigned short` in `wchar_t` oder `WCHAR`, oder kompilieren Sie "LNK2019g.cpp" über **\/Zc:wchar\_t\-**.