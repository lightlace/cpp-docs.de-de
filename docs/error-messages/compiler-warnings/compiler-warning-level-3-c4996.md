---
title: Compilerwarnung (Stufe 3) C4996 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4996
dev_langs:
- C++
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
caps.latest.revision: 34
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
ms.sourcegitcommit: b790beb88de009e1c7161f3c9af6b3e21c22fd8e
ms.openlocfilehash: aa9586bd0abed0b1fa1d24c777eea8c82c5cedc0
ms.lasthandoff: 03/29/2017

---
# <a name="compiler-warning-level-3-c4996"></a>Compilerwarnung (Stufe 3) C4996
Der Compiler hat eine veraltete Deklaration gefunden.  
  
 Diese Warnung/dieser Fehler hat mehrere Bedeutungen.  
  
 `C4996`Tritt auf, wenn der Compiler erkennt, eine Funktion oder Variable mit der Kennzeichnung [veraltet](../../cpp/deprecated-cpp.md). Verschiedene Funktionen, Memberfunktionen, Vorlagenfunktionen und globale Variablen in den in Visual Studio enthaltenen Bibliotheken sind als veraltet gekennzeichnet. Möglicherweise besteht für diese Funktionen ein anderer, bevorzugter Name, sie sind unsicher oder in einer sichereren Variante verfügbar oder schlicht veraltet. Die Fehlermeldung gibt möglicherweise eine Ersatzvorschlag für die veraltete Funktion oder globale Variable an. Sie können diese Warnung deaktivieren, mit der [Warnung](../../preprocessor/warning.md) Pragmas oder der **/wd4996** -Befehlszeilenoption. Bestimmte Klassen von Veraltungswarnungen können auch mithilfe von Präprozessormakros deaktiviert werden. 

Diese Warnung wird auch ausgegeben, wenn Sie versuchen, Zugriff auf eine Funktion, die Klassenmember oder Typedef, die die C ++ 14 `[[deprecated]]` Attribut. Weitere Informationen finden Sie unter [Standard C++-Attribute](../../cpp/attributes2.md). 
  
 **Der POSIX-Name für dieses Element ist veraltet. Verwenden Sie stattdessen die ISO C- und C++-konformen Namen:** New_name**. Details finden Sie in der Onlinehilfe.**  
  
 Einige POSIX-Funktionen in der CRT wurden umbenannt, um sie mit den in C99 und C++03 festgelegten Regeln für Namen von implementierungsdefinierten globalen Funktionen konform zu machen. In den meisten Fällen wurde dem POSIX-Funktionsnamen ein führender Unterstrich hinzugefügt, um einen mit dem Standard konformen Namen zu erzielen. Der Compiler gibt für die ursprünglichen Funktionsnamen eine Veraltungswarnung aus und schlägt den bevorzugten Namen vor. Nur die ursprünglichen Namen sind veraltet, nicht die Funktionen selbst. Um die Veraltungswarnungen für diese Funktionen zu deaktivieren, definieren Sie das Präprozessor-Makro **_CRT_NONSTDC_NO_WARNINGS**. Sie können dies auf der Befehlszeile durch Einschließen der Option `/D_CRT_NONSTDC_NO_WARNINGS`definieren. Um dieses Makro in Visual Studio zu definieren, öffnen Sie das **Eigenschaftenseiten** -Dialogfeld für Ihr Projekt. Erweitern Sie **Konfigurationseigenschaften**, **C/C++**, **Präprozessor**. Fügen Sie in den **Präprozessordefinitionen** `_CRT_NONSTDC_NO_WARNINGS`hinzu. Wählen Sie **OK** aus, um Ihre Änderung zu speichern, und erstellen Sie das Projekt anschließend neu. Um dieses Makro nur in bestimmten Quelldateien zu definieren, fügen Sie die Zeile `#define _CRT_NONSTDC_NO_WARNINGS` vor jeder Zeile hinzu, die eine Headerdatei einbindet.  
  
 **Diese Funktion oder Variable möglicherweise unsicher. Erwägen Sie** sichere_version **stattdessen. Zum Deaktivieren der Veraltungswarnung verwenden Sie „_CRT_SECURE_NO_WARNINGS“.  Details finden Sie in der Onlinehilfe.**  
  
 Einige CRT- und C++-Standardbibliothek Funktionen und globale Variablen wurden zugunsten von neuen, sichereren Funktionen als veraltet markiert. Der Compiler gibt für diese Funktionen eine Veraltungswarnung aus und schlägt die bevorzugte Funktion vor. Um die Veraltungswarnungen für diese Funktionen in der CRT zu deaktivieren, definieren Sie **_CRT_SECURE_NO_WARNINGS**. Zum Deaktivieren der Warnungen zu veralteten globalen Variablen definieren Sie **_CRT_SECURE_NO_WARNINGS_GLOBALS**. Weitere Informationen zu diesen Funktionen als veraltet markierte Funktionen und globale Variablen finden Sie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) und [sichere Bibliotheken: C++-Standardbibliothek](../../standard-library/safe-libraries-cpp-standard-library.md).  
  
 **Funktionsaufruf mit Parametern, die ggf. unsicher - verwendet diesen Aufruf der Aufrufer sicherstellen, dass die übergebenen Werte richtig sind. Sie können diese Warnung mit D_SCL_SECURE_NO_WARNINGS deaktivieren. Dokumentation zum Verwenden von Visual C++ "Überprüfte Iteratoren" finden Sie unter**  
  
 Bestimmte Vorlagenfunktionen der C++-Standardbibliothek überprüfen Parameter nicht auf Richtigkeit. Diese Warnung hilft Ihnen, die Verwendung dieser Funktionen zu erkennen. Um die Warnungen für diese Funktionen zu deaktivieren, definieren Sie **_SCL_SECURE_NO_WARNINGS**. Weitere Informationen finden Sie unter [Checked Iterators (Überprüfte Iteratoren)](../../standard-library/checked-iterators.md).  
  
 **Diese Funktion oder Variable wurde durch neuere Bibliothek oder einem Betriebssystem-Funktionalität ersetzt. Erwägen Sie** neues_element **stattdessen. Details finden Sie in der Onlinehilfe.**  
  
 Einige Bibliotheksfunktionen und globale Variablen wurden als veraltet gekennzeichnet. Diese Funktionen und Variablen werden möglicherweise in einer zukünftigen Version der Bibliothek entfernt. Der Compiler gibt für diese Elemente eine Veraltungswarnung aus und schlägt die bevorzugte Alternative vor. Um die Veraltungswarnungen für diese Elemente zu deaktivieren, definieren Sie **_CRT_OBSOLETE_NO_WARNINGS**. Weitere Informationen finden Sie in der Dokumentation für die veraltete Funktion oder Variable.  
  
 **Verschiedene Nachrichten in MFC- oder ATL-code**  
  
 `C4996` kann auch bei der Verwendung von MFC-Funktionen oder ATL-Funktionen auftreten, die aus Sicherheitsgründen nicht mehr implementiert wurden. Um diese Warnungen zu unterdrücken, finden Sie unter [_AFX_SECURE_NO_WARNINGS](http://msdn.microsoft.com/Library/97dcfd41-1e56-41d5-bf7e-d240b950134b) und [_ATL_SECURE_NO_WARNINGS](http://msdn.microsoft.com/Library/587d29d8-a75a-44a3-bec8-f724087e5e73).  
  
 **Marshalling von Fehlern in CLR-code**  
  
 `C4996` kann auch auftreten, wenn Sie die Marshallingbibliothek verwenden. In diesem Fall ist C4996 ein Fehler, keine Warnung. Dieser Fehler tritt bei der Verwendung [Marshal_as](../../dotnet/marshal-as.md) zum Konvertieren zwischen zwei Datentypen, die erfordern einen [Marshal_context-Klasse](../../dotnet/marshal-context-class.md). Der Fehler wird auch angezeigt, wenn die Marshallingbibliothek keine Konvertierung unterstützt. Weitere Informationen über die Marshallingbibliothek finden Sie unter [Overview of Marshaling in C++](../../dotnet/overview-of-marshaling-in-cpp.md).  
  
 **Beispiele, die C4996 generieren**  
  
 Im ersten Beispiel wird `C4996` für die Zeile generiert, in der die Funktion deklariert wird, sowie für die Zeile, in der die Funktion verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4996 generiert.  
  
```cpp  
// C4996.cpp  
// compile with: /W3  
// C4996 warning expected  
#include <stdio.h>  
  
// #pragma warning(disable : 4996)  
void func1(void) {  
   printf_s("\nIn func1");  
}  
  
__declspec(deprecated) void func1(int) {  
   printf_s("\nIn func2");  
}  
  
int main() {  
   func1();  
   func1(1);  
}  
```  
  
## <a name="example"></a>Beispiel  
 C4996 kann auch auftreten, wenn Sie beim Kompilieren mit `_ITERATOR_DEBUG_LEVEL` keinen überprüften Iterator definieren (dieser ist beim Buildvorgang im Debugmodus standardmäßig auf 1 festgelegt).  Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../../standard-library/checked-iterators.md) .  
  
 Im folgenden Codebeispiel wird von C++-Standardbibliothek wird C4996 erzeugt.  
  
```cpp  
// C4996_b.cpp  
// compile with: /EHsc /W3 /c  
#define _ITERATOR_DEBUG_LEVEL 1  
  
#include <algorithm>  
#include <iterator>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
    int a[] = { 1, 2, 3 };  
    int b[] = { 10, 11, 12 };  
    copy(a, a + 3, b + 1);   // C4996  
    // try the following line instead  
    //   copy(a, a + 3, b);  
    copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK  
}  
  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird von C++-Standardbibliothek wird C4996 als Warnung generiert. Das Beispiel enthält Inlinekommentare.  
  
```cpp  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <iterator>  
#include <numeric>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v(16);  
    iota(v.begin(), v.end(), 0);  
    print("v: ", v);  
  
    // OK: vector::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to C++ Standard Library algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (i.e. an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (i.e. it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4996 erzeugt, weil die Marshallingbibliothek einen Kontext benötigt, um von `System::String` in `const char *`zu konvertieren.  
  
```cpp  
// C4996_Marshal.cpp  
// compile with: /clr   
// C4996 expected  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = marshal_as<const char*>( message );  
   return 0;  
}  
```
