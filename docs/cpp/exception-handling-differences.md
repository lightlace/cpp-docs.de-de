---
title: Strukturierte Ausnahmebehandlung in C++
ms.date: 08/14/2018
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
ms.openlocfilehash: 2c4f1a8c3729e2b4d49a0152425e57717f7e9997
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154404"
---
# <a name="handle-structured-exceptions-in-c"></a>Strukturierte Ausnahmebehandlung in C++

Der Hauptunterschied zwischen C strukturierte Ausnahmebehandlung (SEH) und C++-Ausnahmebehandlung ist, dass die C++-Ausnahmebehandlung Typen behandelt, während C Modell für die strukturierte Ausnahmebehandlung mit Ausnahmen eines bestimmten Typs behandelt; insbesondere **ganze Zahl ohne Vorzeichen**. Das bedeutet, dass C-Ausnahmen über einen Ganzzahlwert ohne Vorzeichen identifiziert werden und C++-Ausnahmen über den Datentyp. Wenn eine strukturierte Ausnahme in C++ ausgelöst wird, führt jeder mögliche Handler einen Filter, der die C-Ausnahmekontext überprüft und bestimmt, ob die Ausnahme akzeptiert, an einen anderen Handler übergeben oder ignoriert wird. Wenn eine Ausnahme in C++ ausgelöst wird, kann sie einem beliebigen Typ angehören.

Der zweite Unterschied ist, dass die strukturierte C-Ausnahmemodell Behandlung als bezeichnet *asynchrone*, da Ausnahmen, die normale ablaufsteuerung sekundären auftreten. Der C++-Ausnahmebehandlungsmechanismus ist vollständig *synchrone*, was bedeutet, dass Ausnahmen auftreten, nur, wenn sie ausgelöst werden.

Bei Verwendung der [/EHs "oder" / EHsc](../build/reference/eh-exception-handling-model.md) -Compileroption, die keine C++-Ausnahme-Handler Handle strukturierte Ausnahmen. Diese Ausnahmen behandelt werden, nur von **__catch** strukturierte Ausnahmehandler oder **__finally** Beendigungshandler strukturiert. Weitere Informationen finden Sie unter [Structured Exception Handling (C/C++)](structured-exception-handling-c-cpp.md).

Unter den [/EHa](../build/reference/eh-exception-handling-model.md) -Compileroption verwenden, wenn in einem C++-Programm eine C-Ausnahme ausgelöst wird, es kann behandelt werden von einem strukturierten Ausnahmehandler mit dem zugeordneten Filter oder einem C++ **catch** Handler, je nachdem, was ist dynamisch dem Ausnahmekontext. Das folgende C++-Programm löst z. B. eine C-Ausnahme innerhalb eines C++ **versuchen** Kontext:

## <a name="example---catch-a-c-exception-in-a-c-catch-block"></a>Beispiel: Catch eine C-Ausnahme in einem C++-catch-block

```cpp
// exceptions_Exception_Handling_Differences.cpp
// compile with: /EHa
#include <iostream>

using namespace std;
void SEHFunc( void );

int main() {
   try {
      SEHFunc();
   }
   catch( ... ) {
      cout << "Caught a C exception."<< endl;
   }
}

void SEHFunc() {
   __try {
      int x, y = 0;
      x = 5 / y;
   }
   __finally {
      cout << "In finally." << endl;
   }
}
```

```Output
In finally.
Caught a C exception.
```

## <a name="c-exception-wrapper-classes"></a>Wrapperklassen für C-Ausnahme

In einem einfachen Beispiel wie oben, die C-Ausnahme abgefangen werden kann, nur durch ein Auslassungszeichen (**...** ) **catch** Handler. Es werden keine Informationen über den Typ oder die Art der Ausnahme an den Handler übermittelt. Diese Methode funktioniert, zwar möglicherweise in einigen Fällen möchten eine Transformation zwischen den beiden ausnahmebehandlungsmodellen definieren, damit jede C-Ausnahme mit einer bestimmten Klasse verknüpft ist. Dazu können Sie eine Wrapperklasse für eine C-Ausnahme definieren, die verwendet oder abgeleitet werden kann, um einer C-Ausnahme einen speziellen Klassentyp zuzuordnen. Auf diese Weise jede C-Ausnahme verarbeitet werden kann separat von einem bestimmten C++ **catch** Ereignishandler anstelle aller Textknoten in einem einzelnen Ereignishandler.

Die Wrapperklasse enthält eventuell eine Schnittstelle, die aus mehreren Memberfunktionen besteht, die den Wert der Ausnahme bestimmen und auf die erweiterten Ausnahmekontextinformationen zugreifen, die vom C-Ausnahmemodell bereitgestellt werden. Sie können auch festlegen, einen Standardkonstruktor und einen Konstruktor, akzeptiert eine **ganze Zahl ohne Vorzeichen** Argument (um für die zugrunde liegende C-Ausnahme-Darstellung bereitzustellen), und einen Konstruktor für bitweise Kopien. Hier ist eine mögliche Implementierung einer C-Ausnahme-Wrapperklasse:

```cpp
// exceptions_Exception_Handling_Differences2.cpp
// compile with: /c
class SE_Exception {
private:
   SE_Exception() {}
   SE_Exception( SE_Exception& ) {}
   unsigned int nSE;
public:
   SE_Exception( unsigned int n ) : nSE( n ) {}
   ~SE_Exception() {}
   unsigned int getSeNumber() {
      return nSE;
   }
};
```

Um diese Klasse verwenden zu können, installieren Sie eine benutzerdefinierte C-Ausnahme Translation-Funktion, die aufgerufen wird, werden der internen Ausnahmebehandlungsmechanismus jedes Mal, wenn eine C-Ausnahme ausgelöst wird. In der Übersetzungsfunktion können Sie eine beliebige typisierte Ausnahme auslösen (z. B. eine `SE_Exception` Typ oder einen Klassentyp abgeleitet `SE_Exception`), die abgefangen werden kann, von einem entsprechenden übereinstimmenden C++ **catch** Handler. Die Übersetzungsfunktion kann einfach zurückkehren. Sie hat also die Ausnahme nicht bearbeitet. Wenn die Übersetzungsfunktion selbst eine C-Ausnahme auslöst [beenden](../c-runtime-library/reference/terminate-crt.md) aufgerufen wird.

Um eine benutzerdefinierte Übersetzungsfunktion anzugeben, rufen die [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) Funktion mit dem Namen Ihrer Übersetzungsfunktion als einziges Argument. Die Übersetzungsfunktion, die Sie schreiben wird einmal für jeden Funktionsaufruf im Stapel mit aufgerufen **versuchen** Blöcke. Es gibt keine standardmäßige Übersetzungsfunktion; Wenn Sie nicht durch den Aufruf angeben **_set_se_translator**, die C-Ausnahme kann nur durch ein Auslassungszeichen aufgefangen **catch** Handler.

## <a name="example---use-a-custom-translation-function"></a>Beispiel: Verwenden Sie eine benutzerdefinierte Übersetzungsfunktion

Der folgende Code installiert beispielsweise eine benutzerdefinierte Übersetzungsfunktion und löst anschließend eine C-Ausnahme aus, die von der `SE_Exception`-Klasse umschlossen wird:

```cpp
// exceptions_Exception_Handling_Differences3.cpp
// compile with: /EHa
#include <stdio.h>
#include <eh.h>
#include <windows.h>

class SE_Exception {
private:
   SE_Exception() {}
   unsigned int nSE;
public:
   SE_Exception( SE_Exception& e) : nSE(e.nSE) {}
   SE_Exception(unsigned int n) : nSE(n) {}
   ~SE_Exception() {}
   unsigned int getSeNumber() { return nSE; }
};

void SEFunc() {
    __try {
        int x, y = 0;
        x = 5 / y;
    }
    __finally {
        printf_s( "In finally\n" );
    }
}

void trans_func( unsigned int u, _EXCEPTION_POINTERS* pExp ) {
    printf_s( "In trans_func.\n" );
    throw SE_Exception( u );
}

int main() {
    _set_se_translator( trans_func );
    try {
        SEFunc();
    }
    catch( SE_Exception e ) {
        printf_s( "Caught a __try exception with SE_Exception.\n" );
        printf_s( "nSE = 0x%x\n", e.getSeNumber() );
    }
}
```

```Output
In trans_func.
In finally
Caught a __try exception with SE_Exception.
nSE = 0xc0000094
```

## <a name="see-also"></a>Siehe auch

[Kombination von C (strukturierte) und C++-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)
