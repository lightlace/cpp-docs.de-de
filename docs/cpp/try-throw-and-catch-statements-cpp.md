---
title: try-, throw- und catch-Anweisungen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- catch_cpp
- try_cpp
- throw_cpp
dev_langs:
- C++
helpviewer_keywords:
- catch keyword [C++]
- keywords [C++], exception handling
- C++ exception handling, statement syntax
- try-catch keyword [C++], about try-catch exception handling
- throw keyword [C++]
- try-catch keyword [C++]
- try-catch keyword [C++], exception handling
- throwing exceptions [C++], throw keyword
- try-catch keyword [C++], throw keyword [C++]s
- throwing exceptions [C++], implementing C++ exception handling
- throwing exceptions [C++]
- throw keyword [C++], throw() vs. throw(...)
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8454df8f8f66264e1e877a1e1504f4266944fa7a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118894"
---
# <a name="try-throw-and-catch-statements-c"></a>try-, throw- und catch-Anweisungen (C++)

Um Ausnahmebehandlung in C++ zu implementieren, verwenden Sie **versuchen**, **auslösen**, und **catch** Ausdrücke.

Verwenden Sie zunächst eine **versuchen** Block, um eine oder mehrere Anweisungen einschließen, der möglicherweise eine Ausnahme auslöst.

Ein **auslösen** -Ausdruck signalisiert, dass eine außergewöhnliche Bedingung – oftmals ein Fehler, aufgetreten eine **versuchen Sie es** Block. Sie können ein Objekt eines beliebigen Typs als Operand einer **auslösen** Ausdruck. Normalerweise wird dieses Objekt verwendet, um Informationen über den Fehler zu kommunizieren. In den meisten Fällen empfiehlt es sich, dass Sie verwenden die [Std:: Exception](../standard-library/exception-class.md) mindestens eine Klasse die abgeleiteten Klassen, die in der Standardbibliothek definiert sind. Wenn eine davon nicht passend ist, wird empfohlen, dass Sie Ihre eigene Ausnahmeklasse von `std::exception` ableiten.

Um Ausnahmen zu behandeln, die ausgelöst werden können, implementiert wird, eine oder mehrere **catch** Blöcke, die unmittelbar nach einer **versuchen** Block. Jede **catch** -Block gibt den Typ der Ausnahme, die sie behandeln kann.

Dieses Beispiel zeigt eine **versuchen** -Block und seine Handler. Nehmen Sie an, dass `GetNetworkResource()` Daten über eine Netzwerkverbindung erhält und dass die beiden Ausnahmetypen benutzerdefinierte Klassen sind, die von `std::exception` abgeleitet sind. Beachten Sie, die durch die Ausnahmen abgefangen werden **const** verweisen in der **catch** Anweisung. Es wird empfohlen, dass Sie die Ausnahmen nach Wert auslösen und sie durch einen const-Verweis abfangen.

## <a name="example"></a>Beispiel

```cpp
MyData md;
try {
   // Code that could throw an exception
   md = GetNetworkResource();
}
catch (const networkIOException& e) {
   // Code that executes when an exception of type
   // networkIOException is thrown in the try block
   // ...
   // Log error message in the exception object
   cerr << e.what();
}
catch (const myDataFormatException& e) {
   // Code that handles another exception type
   // ...
   cerr << e.what();
}

// The following syntax shows a throw expression
MyData GetNetworkResource()
{
   // ...
   if (IOSuccess == false)
      throw networkIOException("Unable to connect");
   // ...
   if (readError)
      throw myDataFormatException("Format error");
   // ...
}
```

## <a name="remarks"></a>Hinweise

Den Code nach der **versuchen** -Klausel ist der abgesicherte Codeabschnitt. Die **auslösen** Ausdruck *löst*– d. h. löst – eine Ausnahme. Der Codeblock nach der **catch** -Klausel ist der Ausnahmehandler. Dies ist der Handler, *fängt* die Ausnahme, die ausgelöst wird, wenn die Typen in der **auslösen** und **catch** Ausdrücke kompatibel sind. Eine Liste der Regeln, die in typübereinstimmung gelten **catch** -Blöcken finden Sie unter [wie Catch-Blöcke ausgewertet werden](../cpp/how-catch-blocks-are-evaluated-cpp.md). Wenn die **catch** -Anweisung gibt ein Auslassungszeichen (...) anstelle eines Typs, der **catch** -Block verarbeitet jede Art von Ausnahme. Beim Kompilieren mit der [/EHa](../build/reference/eh-exception-handling-model.md) Option dazu können gehören, C-strukturierte Ausnahmen und vom System generierte oder der Anwendung generierte asynchrone Ausnahmen wie z. B. Arbeitsspeicher, aufgrund einer Division durch Null und fließkommaverletzungen Verstöße gegen den Zugriffsschutz . Da **catch** Blöcke werden verarbeitet, in der programmreihenfolge auf einen übereinstimmenden Typ zu finden, ein Handler für die Schaltfläche muss der letzte Handler für das zugeordnete **versuchen** Block. Verwenden Sie `catch(...)` mit Vorsicht. Lassen Sie nicht zu, dass ein Programm fortgesetzt wird, es sei denn der catch-Block kann die spezifische Ausnahme, die abgefangen wird, behandeln. Normalerweise wird ein `catch(...)`-Block verwendet, um Fehler zu protokollieren und eine spezielle Bereinigung vor dem Beenden der Programmausführung auszuführen.

Ein **auslösen** -Ausdruck, der ohne Operanden löst erneut die Ausnahme, die gerade verarbeitet wird. Wir empfehlen diese Form, wenn die Ausnahme erneut ausgelöst wird, denn dadurch wird die originale polymorphe Typinformation der Ausnahme bewahrt. Ein solcher Ausdruck sollte nur verwendet werden, einem **catch** Handler oder in eine Funktion, die aufgerufen wird eine **catch** Handler. Das erneut ausgelöste Ausnahmeobjekt ist das ursprüngliche Ausnahmeobjekt (keine Kopie).

```cpp
try {
   throw CSomeOtherException();
}
catch(...) {
   // Catch all exceptions - dangerous!!!
   // Respond (perhaps only partially) to the exception, then
   // re-throw to pass the exception to some other handler
   // ...
   throw;
}
```

## <a name="see-also"></a>Siehe auch

[C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Nicht behandelte C++-Ausnahmen](../cpp/unhandled-cpp-exceptions.md)<br/>
[__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)