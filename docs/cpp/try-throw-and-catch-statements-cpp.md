---
title: "try-, throw- und catch-Anweisungen (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "catch_cpp"
  - "throw"
  - "try_cpp"
  - "try"
  - "throw_cpp"
  - "catch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "catch-Schlüsselwort [C++]"
  - "Schlüsselwörter [C++], Behandlung von Ausnahmen"
  - "C++-Ausnahmebehandlung Anweisungssyntax"
  - "Try-Catch-Schlüsselwort [C++], Informationen über Try-Catch-Ausnahmebehandlung"
  - "throw-Schlüsselwort [C++]"
  - "try-catch-Schlüsselwort [C++]"
  - "Try-Catch-Schlüsselwort [C++], Behandlung von Ausnahmen"
  - "Auslösen von Ausnahmen, throw-Schlüsselwort"
  - "Try-Catch-Schlüsselwort [C++], throw-Schlüsselwort [C++]"
  - "Auslösen von Ausnahmen, die Implementierung der C++-Ausnahmebehandlung"
  - "Auslösen von Ausnahmen"
  - "throw-Schlüsselwort [C++], throw() im Vergleich zu throw(...)"
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
caps.latest.revision: 24
caps.handback.revision: "24"
ms.author: "mblome"
manager: "ghogen"
---
# try-, throw- und catch-Anweisungen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um die Ausnahmebehandlung in C++ zu implementieren, verwenden Sie die Ausdrücke `try`, `throw` und `catch`.  
  
 Verwenden Sie zuerst einen `try`-Block, um eine oder mehrere Anweisungen zu umschließen, die eventuell eine Ausnahme auslösen.  
  
 Ein `throw`-Ausdruck signalisiert, dass ein Ausnahmezustand – oftmals ein Fehler – in einem `try`-Block aufgetreten ist. Sie können ein Objekt beliebigen Typs als Operand eines `throw`-Ausdrucks verwenden. Normalerweise wird dieses Objekt verwendet, um Informationen über den Fehler zu kommunizieren. In den meisten Fällen empfiehlt es sich, die Verwendung der [Std:: Exception](../standard-library/exception-class1.md) -Klasse oder einer der abgeleiteten Klassen, die in der Standardbibliothek definiert sind. Wenn eine davon nicht passend ist, wird empfohlen, dass Sie Ihre eigene Ausnahmeklasse von `std::exception` ableiten.  
  
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
 Der Code nach der `try`-Klausel ist der abgesicherte Codeabschnitt. Die `throw` Ausdruck *löst*– d. h. löst – eine Ausnahme. Der Codeblock nach der `catch`-Klausel ist der Ausnahmehandler. Dies ist der Handler, *fängt* die Ausnahme, die ausgelöst wird, wenn die Typen in der `throw` und `catch` Ausdrücke kompatibel sind. Eine Liste der Regeln, im Typ übereinstimmende `catch` -Blöcken finden Sie unter [wie Catch-Blöcke ausgewertet werden](../cpp/how-catch-blocks-are-evaluated-cpp.md). Wenn die `catch`-Anweisung ein Auslassungszeichen (...) statt eines Typs festlegt, behandelt der `catch`-Block jeden Ausnahmetyp. Beim Kompilieren mit der [/EHa](../build/reference/eh-exception-handling-model.md) Option, dazu gehören C-strukturierte Ausnahmen und vom System generierte oder der Anwendung generierte asynchrone Ausnahmen wie z. B. Arbeitsspeicher Schutz aufgrund einer Division durch Null und fließkommaverletzungen. Da `catch`-Blöcke in der Programmabfolge verarbeitet werden, um einen übereinstimmenden Typ zu finden, muss ein Auslassungshandler der letzte Handler für den zugeordneten `try`-Block sein. Verwenden Sie `catch(...)` mit Vorsicht. Lassen Sie nicht zu, dass ein Programm fortgesetzt wird, es sei denn der catch-Block kann die spezifische Ausnahme, die abgefangen wird, behandeln. Normalerweise wird ein `catch(...)`-Block verwendet, um Fehler zu protokollieren und eine spezielle Bereinigung vor dem Beenden der Programmausführung auszuführen.  
  
 Ein `throw`-Ausdruck ohne Operanden löst erneut die Ausnahme aus, die gerade verarbeitet wird. Wir empfehlen diese Form, wenn die Ausnahme erneut ausgelöst wird, denn dadurch wird die originale polymorphe Typinformation der Ausnahme bewahrt. Ein solcher Ausdruck sollte nur in einem `catch`-Handler oder in einer Funktion verwendet werden, die von einem `catch`-Handler aus aufgerufen wird. Das erneut ausgelöste Ausnahmeobjekt ist das ursprüngliche Ausnahmeobjekt (keine Kopie).  
  
```  
try {  
   throw CSomeOtherException();  
}  
catch(...) {  
   // Catch all exceptions – dangerous!!!  
   // Respond (perhaps only partially) to the exception, then  
   // re-throw to pass the exception to some other handler  
   // ...  
   throw;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Nicht behandelte C++-Ausnahmen](../cpp/unhandled-cpp-exceptions.md)   
 [__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)