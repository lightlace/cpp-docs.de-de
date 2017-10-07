---
title: Versuchen Sie es, throw- und catch-Anweisungen (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 89db418a92239460379d1ea41d2d49a8073095c2
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="try-throw-and-catch-statements-c"></a>try-, throw- und catch-Anweisungen (C++)
Um die Ausnahmebehandlung in C++ zu implementieren, verwenden Sie die Ausdrücke `try`, `throw` und `catch`.  
  
 Verwenden Sie zuerst einen `try`-Block, um eine oder mehrere Anweisungen zu umschließen, die eventuell eine Ausnahme auslösen.  
  
 Ein `throw`-Ausdruck signalisiert, dass ein Ausnahmezustand – oftmals ein Fehler – in einem `try`-Block aufgetreten ist. Sie können ein Objekt beliebigen Typs als Operand eines `throw`-Ausdrucks verwenden. Normalerweise wird dieses Objekt verwendet, um Informationen über den Fehler zu kommunizieren. In den meisten Fällen wird empfohlen, Sie verwenden die [Std:: Exception](../standard-library/exception-class.md) Klasse oder einer der abgeleiteten Klassen, die in der Standardbibliothek definiert sind. Wenn eine davon nicht passend ist, wird empfohlen, dass Sie Ihre eigene Ausnahmeklasse von `std::exception` ableiten.  
  
 Um Ausnahmen zu behandeln, die möglicherweise ausgelöst werden, implementieren Sie einen oder mehrere `catch`-Blöcke, die unmittelbar einem `try`-Block folgen. Jeder `catch`-Block gibt den Ausnahmetyp an, den er behandeln kann.  
  
 Dieses Beispiel zeigt einen `try`-Block und seine Handler. Nehmen Sie an, dass `GetNetworkResource()` Daten über eine Netzwerkverbindung erhält und dass die beiden Ausnahmetypen benutzerdefinierte Klassen sind, die von `std::exception` abgeleitet sind. Beachten Sie, dass die Ausnahmen durch den `const`-Verweis in der `catch`-Anweisung auftreten. Es wird empfohlen, dass Sie die Ausnahmen nach Wert auslösen und sie durch einen const-Verweis abfangen.  
  
## <a name="example"></a>Beispiel  
  
```  
  
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
 Der Code nach der `try`-Klausel ist der abgesicherte Codeabschnitt. Die `throw` Ausdruck *löst*– d. h. löst – eine Ausnahme. Der Codeblock nach der `catch`-Klausel ist der Ausnahmehandler. Dies ist der Handler, *fängt* die Ausnahme, die ausgelöst wird, wenn die Typen in der `throw` und `catch` Ausdrücke kompatibel sind. Eine Liste der Regeln, die Typ-Abgleich im steuern `catch` -Blöcken finden Sie unter [wie Catch-Blöcke ausgewertet werden](../cpp/how-catch-blocks-are-evaluated-cpp.md). Wenn die `catch`-Anweisung ein Auslassungszeichen (...) statt eines Typs festlegt, behandelt der `catch`-Block jeden Ausnahmetyp. Bei der Kompilierung mit der [/EHa](../build/reference/eh-exception-handling-model.md) Option dazu können gehören, C-strukturierte Ausnahmen und vom System generierte oder der Anwendung generierte asynchrone Ausnahmen, z. B. Arbeitsspeicher Schutz aufgrund einer Division durch Null und fließkommaverletzungen . Da `catch`-Blöcke in der Programmabfolge verarbeitet werden, um einen übereinstimmenden Typ zu finden, muss ein Auslassungshandler der letzte Handler für den zugeordneten `try`-Block sein. Verwenden Sie `catch(...)` mit Vorsicht. Lassen Sie nicht zu, dass ein Programm fortgesetzt wird, es sei denn der catch-Block kann die spezifische Ausnahme, die abgefangen wird, behandeln. Normalerweise wird ein `catch(...)`-Block verwendet, um Fehler zu protokollieren und eine spezielle Bereinigung vor dem Beenden der Programmausführung auszuführen.  
  
 Ein `throw`-Ausdruck ohne Operanden löst erneut die Ausnahme aus, die gerade verarbeitet wird. Wir empfehlen diese Form, wenn die Ausnahme erneut ausgelöst wird, denn dadurch wird die originale polymorphe Typinformation der Ausnahme bewahrt. Ein solcher Ausdruck sollte nur in einem `catch`-Handler oder in einer Funktion verwendet werden, die von einem `catch`-Handler aus aufgerufen wird. Das erneut ausgelöste Ausnahmeobjekt ist das ursprüngliche Ausnahmeobjekt (keine Kopie).  
  
```  
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
 [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Nicht behandelte C++-Ausnahmen](../cpp/unhandled-cpp-exceptions.md)   
 [__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)
