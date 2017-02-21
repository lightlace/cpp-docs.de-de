---
title: "/Zc:implicitNoexcept (implizite Ausnahmespezifizierer) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:implicitNoexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc:implicitNoexcept"
  - "Zc:implicitNoexcept"
  - "-Zc:implicitNoexcept"
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Zc:implicitNoexcept (implizite Ausnahmespezifizierer)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn die **\/Zc:implicitNoexcept**\-Option angegeben ist, fügt der Compiler den speziellen vom Compiler definierten Memberfunktionen und benutzerdefinierten Destruktoren und Deallokatoren einen impliziten [noexcept](../../cpp/noexcept-cpp.md)\-Ausnahmebezeichner hinzu.  **\/Zc:implicitNoexcept** ist gemäß dem ISO\-Standard C\+\+11 standardmäßig aktiviert.  Durch Deaktivieren dieser Option wird für das implizite `noexcept`\-Element für benutzerdefinierte Destruktoren und Deallokatoren und die speziellen vom Compiler definierten Memberfunktionen deaktiviert.  
  
## Syntax  
  
```vb  
/Zc:implicitNoexcept[-]  
```  
  
#### Parameter  
  
## Hinweise  
 In der Standardeinstellung und wenn **\/Zc:implicitNoexcept** angegeben ist, folgt der Compiler dem Abschnitt 15.4 des ISO\-Standards C\+\+11 und fügt jeder implizit deklarierten oder explizit als Standard festgelegten speziellen Memberfunktion – dem Standardkonstruktor, Kopierkonstruktor, Bewegungskonstruktor, Destruktor, Kopierzuweisungsoperator oder dem Bewegungszuweisungsoperator – und jeder benutzerdefinierten Destruktor\- oder Deallokatorfunktion implizit einen `noexcept`\-Ausnahmebezeichner hinzu.  Ein benutzerdefinierter Deallokator verfügt über einen impliziten `noexcept(true)`\-Ausnahmebezeichner.  Für benutzerdefinierte Destruktoren ist `noexcept(true)` der implizite Ausnahmebezeichner, es sei denn eine enthaltene Elementklasse oder Basisklasse weist einen Destruktor auf, der nicht `noexcept(true)` ist.  Für vom Compiler generierte spezielle Memberfunktionen ist `noexcept(false)` der implizite Ausnahmebezeichner, wenn eine von dieser Funktion aufgerufene Funktion `noexcept(false)` ist.  Andernfalls ist `noexcept(true)` der implizite Ausnahmebezeichner.  
  
 Für Funktionen, die mit expliziten `noexcept`\- oder `throw`\-Bezeichnern oder einem `__declspec(nothrow)`\-Attribut deklariert wurden, generiert der Compiler keinen impliziten Ausnahmebezeichner.  
  
 Wenn diese Option durch Angabe von **\/Zc:implicitNoexcept\-** deaktiviert ist, werden keine impliziten Ausnahmebezeichner vom Compiler generiert.  Dieses Verhalten ist mit dem in Visual Studio 2013 identisch, wo Destruktoren und Deallokatoren ohne Ausnahmebezeichner über `throw`\-Anweisungen verfügen können.  In der Standardeinstellung und wenn **\/Zc:implicitNoexcept** angegeben ist, wird bei Feststellung einer `throw`\-Anweisung in einer Funktion mit einem impliziten `noexcept(true)`\-Bezeichner zur Laufzeit unmittelbar `std::terminate` aufgerufen, und es kann kein normales Entladungsverhalten für Ausnahmehandler garantiert werden.  Wenn dieser Fall auftritt, generiert der Compiler die [Compilerwarnung \(Stufe 1\) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md).  Wenn `throw` beabsichtigt ist, wird empfohlen, die Funktionsdeklaration so zu ändern, dass sie einen `noexcept(false)`\-Bezeichner enthält, statt **\/Zc:implicitNoexcept\-** zu verwenden.  
  
 In diesem Beispiel wird das Verhalten eines benutzerdefinierten Destruktors ohne expliziten Ausnahmebezeichner veranschaulicht, wenn die **\/Zc:implicitNoexcept**\-Option festgelegt oder deaktiviert ist.  Kompilieren Sie zur Veranschaulichung des Verhaltens, wenn diese festgelegt ist, mithilfe von `cl /EHsc /W4 implicitNoexcept.cpp`.  Kompilieren Sie zur Veranschaulichung des Verhaltens, wenn diese deaktiviert ist, mithilfe von `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`.  
  
```  
// implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp  
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp  
  
#include <iostream>  
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS  
#include <exception>    // for std::set_terminate  
  
void my_terminate()  
{  
    std::cout << "Unexpected throw caused std::terminate" << std::endl;  
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;  
    std::exit(EXIT_FAILURE);  
}  
  
struct A {  
    // Explicit noexcept overrides implicit exception specification  
    ~A() noexcept(false) {  
        throw 1;  
    }  
};  
  
struct B : public A {  
    // Compiler-generated ~B() definition inherits noexcept(false)  
    ~B() = default;  
};  
  
struct C {  
    // By default, the compiler generates an implicit noexcept(true)  
    // specifier for this user-defined destructor. To enable it to  
    // throw an exception, use an explicit noexcept(false) specifier,  
    // or compile by using /Zc:implicitNoexcept-  
    ~C() {    
        throw 1; // C4297, calls std::terminate() at run time  
    }  
};  
  
struct D : public C {  
    // This destructor gets the implicit specifier of its base.  
    ~D() = default;  
};  
  
int main()  
{  
    std::set_terminate(my_terminate);  
  
    try  
    {  
        {  
            B b;   
        }  
    }  
    catch (...)  
    {  
        // exception should reach here in all cases  
        std::cout << "~B Exception caught" << std::endl;  
    }  
    try  
    {  
        {  
            D d;  
        }  
    }  
    catch (...)  
    {  
        // exception should not reach here if /Zc:implicitNoexcept  
        std::cout << "~D Exception caught" << std::endl;  
    }  
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;  
    return EXIT_SUCCESS;  
}  
  
```  
  
 Beim Kompilieren mit der Standardeinstellung **\/Zc:implicitNoexcept** wird mit dem Beispiel die folgende Ausgabe generiert:  
  
  **~B Exception caught**  
**Unexpected throw caused std::terminate**  
**Exit returning EXIT\_FAILURE** Beim Kompilieren mit der Einstellung **\/Zc:implicitNoexcept\-** wird mit dem Beispiel die folgende Ausgabe generiert:  
  
  **~B Exception caught**  
**~D Exception caught**  
**Exit returning EXIT\_SUCCESS** Weitere Informationen über Konformitätsprobleme in Visual C\+\+ finden Sie unter [Nicht dem Standard entsprechendes Verhalten](../../cpp/nonstandard-behavior.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Ändern Sie die Eigenschaft **Zusätzliche Optionen** so, dass **\/Zc:implicitNoexcept** oder **\/Zc:implicitNoexcept\-** eingeschlossen wird, und wählen Sie dann **OK**.  
  
## Siehe auch  
 [\/Zc \(Übereinstimmung\)](../../build/reference/zc-conformance.md)   
 [noexcept](../../cpp/noexcept-cpp.md)   
 [Ausnahmespezifikationen \(throw\)](../../cpp/exception-specifications-throw-cpp.md)   
 [terminate](../Topic/terminate%20\(%3Cexception%3E\).md)