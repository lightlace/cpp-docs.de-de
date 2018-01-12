---
title: '-Zc: ImplicitNoexcept (implizite Ausnahmespezifizierer) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc:implicitNoexcept
dev_langs: C++
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9af0a7a3a175699a4f4b738271fe0d4c5bbac4b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/Zc:implicitNoexcept (implizite Ausnahmespezifizierer)
Wenn die **/Zc: implicitnoexcept** angegeben wird, der Compiler Fügt eine implizite [Noexcept](../../cpp/noexcept-cpp.md) -ausnahmebezeichner Compiler definiert spezielle Memberfunktionen und benutzerdefinierten Destruktoren und deallokatoren. Standardmäßig **/Zc: implicitnoexcept** ist aktiviert, um dem ISO-C ++ 11-standard entsprechen. Durch Deaktivieren dieser Option wird für das implizite `noexcept`-Element für benutzerdefinierte Destruktoren und Deallokatoren und die speziellen vom Compiler definierten Memberfunktionen deaktiviert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
/Zc:implicitNoexcept[-]  
```  
  
#### <a name="parameters"></a>Parameter  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig wird **/Zc: implicitnoexcept** angegeben wird, der Compiler folgt Abschnitt 15.4 des ISO-standard C ++ 11 und fügt implizit eine `noexcept` -ausnahmebezeichner jeder implizit deklarierten oder explizit vorgegebene spezielle Memberfunktion – dem Standardkonstruktor, Kopierkonstruktor, bewegungskonstruktor, Destruktor, Kopierzuweisungsoperator oder bewegungszuweisungsoperator – und jeder benutzerdefinierten Destruktor- oder deallokatorfunktion-Funktion. Ein benutzerdefinierter Deallokator verfügt über einen impliziten `noexcept(true)`-Ausnahmebezeichner. Für benutzerdefinierte Destruktoren ist `noexcept(true)` der implizite Ausnahmebezeichner, es sei denn eine enthaltene Elementklasse oder Basisklasse weist einen Destruktor auf, der nicht `noexcept(true)` ist. Für vom Compiler generierte spezielle Memberfunktionen ist `noexcept(false)` der implizite Ausnahmebezeichner, wenn eine von dieser Funktion aufgerufene Funktion `noexcept(false)` ist. Andernfalls ist `noexcept(true)` der implizite Ausnahmebezeichner.  
  
 Für Funktionen, die mit expliziten `noexcept`- oder `throw`-Bezeichnern oder einem `__declspec(nothrow)`-Attribut deklariert wurden, generiert der Compiler keinen impliziten Ausnahmebezeichner.  
  
 Wenn die Option, durch Angabe deaktiviert ist **/Zc:implicitNoexcept-**, werden keine impliziten ausnahmebezeichner vom Compiler generiert. Dieses Verhalten ist mit dem in Visual Studio 2013 identisch, wo Destruktoren und Deallokatoren ohne Ausnahmebezeichner über `throw`-Anweisungen verfügen können. Standardmäßig und wann **/Zc: implicitnoexcept** angegeben wird, wenn eine `throw` Anweisung gefunden wird, zur Laufzeit in eine Funktion mit einem impliziten `noexcept(true)` Formatbezeichner, wird eine sofortige Aufrufen von `std::terminate`, und normales entladungsverhalten für Ausnahmehandler wird nicht garantiert. Um diese Situation zu identifizieren, generiert der Compiler [Compilerwarnung (Stufe 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md). Wenn die `throw` ist beabsichtigt ist, sollten Sie ändern die Funktionsdeklaration aus, um eine explizite `noexcept(false)` Spezifizierer anstatt **/Zc:implicitNoexcept-**.  
  
 Dieses Beispiel zeigt, wie ein benutzerdefinierte Destruktor, der keine expliziten ausnahmebezeichner Wenn verhält sich die **/Zc: implicitnoexcept** Option festgelegt oder deaktiviert ist. Das Verhalten bei der Einstellung, kompilieren Sie mit `cl /EHsc /W4 implicitNoexcept.cpp`. Um das Verhalten bei deaktivierter anzuzeigen, kompilieren Sie mit `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`.  
  
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
  
 Beim Kompilieren mit der Standardeinstellung **/Zc: implicitnoexcept**, im Beispiel die folgende Ausgabe generiert:  
  
```Output  
~B Exception caught  
Unexpected throw caused std::terminate  
Exit returning EXIT_FAILURE  
```  
  
 Beim Kompilieren mit der Einstellung **/Zc:implicitNoexcept-**, im Beispiel die folgende Ausgabe generiert:  
  
```Output  
~B Exception caught  
~D Exception caught  
Exit returning EXIT_SUCCESS  
```  
  
 Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc: implicitnoexcept** oder **/Zc:implicitNoexcept-** und wählen Sie dann **OK**.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)   
 [noexcept](../../cpp/noexcept-cpp.md)   
 [Ausnahmespezifikationen (Throw)](../../cpp/exception-specifications-throw-cpp.md)   
 [terminate](../../standard-library/exception-functions.md#terminate)