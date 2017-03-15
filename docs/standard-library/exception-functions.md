---
title: '&lt;exception&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c09ac569-5e35-4fe8-872d-ca5810274dd7
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 08d2a2161a2596cebb27175c55023d5313c7b908
ms.lasthandoff: 02/24/2017

---
# <a name="ltexceptiongt-functions"></a>&lt;exception&gt;-Funktionen
||||  
|-|-|-|  
|[current_exception](#current_exception)|[get_terminate](#get_terminate)|[get_unexpected](#get_unexpected)|  
|[make_exception_ptr](#make_exception_ptr)|[rethrow_exception](#rethrow_exception)|[set_terminate](#set_terminate)|  
|[set_unexpected](#set_unexpected)|[terminate](#terminate)|[uncaught_exception](#uncaught_exception)|  
|[unexpected](#unexpected)|  
  
##  <a name="a-namecurrentexceptiona--currentexception"></a><a name="current_exception"></a> current_exception  
 Erhält einen intelligenten Zeiger auf die aktuelle Ausnahme.  
  
```cpp  
exception_ptr current_exception();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)-Objekt, das auf die aktuelle Ausnahme zeigt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die `current_exception`-Funktion in einem catch-Block auf. Wenn eine Ausnahme aktiv ist und die Ausnahme vom catch-Block nicht abgefangen werden kann, gibt die `current_exception`-Funktion ein `exception_ptr`-Objekt zurück, das auf die Ausnahme verweist. Andernfalls gibt die Funktion ein NULL-`exception_ptr`-Objekt zurück.  
  
 Die `current_exception`-Funktion erfasst die Ausnahme, die aktiv ist, unabhängig davon, ob die `catch`-Anweisung eine [exception-declaration](../cpp/try-throw-and-catch-statements-cpp.md)-Anweisung angibt.  
  
 Der Destruktor für die aktuelle Ausnahme wird am Ende des `catch`-Blocks aufgerufen, wenn die Ausnahme nicht erneut ausgelöst wird. Auch wenn Sie die `current_exception`-Funktion im Destruktor aufrufen, gibt die Funktion ein `exception_ptr`-Objekt zurück, das auf die aktuelle Ausnahme verweist.  
  
 Aufeinander folgende Aufrufe der `current_exception`-Funktion geben `exception_ptr`-Objekte zurück, die sich auf unterschiedliche Kopien der aktuellen Ausnahme beziehen. Folglich sind die Objekte bei einem Vergleich ungleich, da sie auf unterschiedliche Kopien verweisen, auch wenn die Kopien den gleichen Binärwert aufweisen.  
  
##  <a name="a-namemakeexceptionptra--makeexceptionptr"></a><a name="make_exception_ptr"></a> make_exception_ptr  
 Erstellt ein [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)-Objekt, das eine Kopie einer Ausnahme enthält.  
  
```cpp  
template <class E>  
exception_ptr make_exception_ptr(E Except);
```  
  
### <a name="parameters"></a>Parameter  
 `Except`  
 Die Klasse mit der zu kopierenden Ausnahme. Normalerweise geben Sie ein [exception class](../standard-library/exception-class.md)-Objekt als Argument für die `make_exception_ptr`-Funktion an, obwohl jedes Klassenobjekt als Argument zulässig ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)-Objekt, das auf eine Kopie der aktuellen Ausnahme für `Except` zeigt.  
  
### <a name="remarks"></a>Hinweise  
 Das Aufrufen der `make_exception_ptr`-Funktion ist gleichbedeutend mit dem Auslösen einer C++-Ausnahme, die in einem catch-Block abgefangen wird, und dem anschließenden Aufrufen der [current_exception](../standard-library/exception-functions.md#current_exception)-Funktion, um ein `exception_ptr`-Objekt zurückzugeben, das auf die Ausnahme verwiest. Die Microsoft-Implementierung der `make_exception_ptr`-Funktion ist effizienter als das Auslösen und anschließende Abfangen einer Ausnahme.  
  
 Eine Anwendung erfordert in der Regel nicht die `make_exception_ptr` -Funktion, und es wird von ihrer Verwendung abgeraten.  
  
##  <a name="a-namerethrowexceptiona--rethrowexception"></a><a name="rethrow_exception"></a> rethrow_exception  
 Löst eine Ausnahme aus, die als Parameter übergeben wird.  
  
```cpp  
void rethrow_exception(exception_ptr P);
```  
  
### <a name="parameters"></a>Parameter  
 `P`  
 Die erneut auszulösende abgefangene Ausnahme. Wenn `P` ein [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)-Element mit dem Wert NULL ist, wird von der Funktion [std::bad_exception](../standard-library/bad-exception-class.md) ausgelöst.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem Sie eine abgefangene Ausnahme in einem `exception_ptr`-Objekt gespeichert haben, kann der primäre Thread das Objekt verarbeiten. Rufen Sie in Ihrem primären Thread die `rethrow_exception`-Funktion zusammen mit dem `exception_ptr`-Objekt als Argument auf. Die `rethrow_exception`-Funktion extrahiert die Ausnahme vom `exception_ptr`-Objekt und löst die Ausnahme anschließend im Kontext des primären Threads aus.  
  
##  <a name="a-namegetterminatea--getterminate"></a><a name="get_terminate"></a> get_terminate  
 Ruft die aktuelle `terminate_handler`-Funktion ab.  
  
```cpp  
terminate_handler get_terminate();
```  
  
##  <a name="a-namesetterminatea--setterminate"></a><a name="set_terminate"></a> set_terminate  
 Richtet ein neues `terminate_handler`-Element ein, das bei Beendigung des Programms aufgerufen wird.  
  
```  
terminate_handler set_terminate(terminate_handler fnew) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `fnew`  
 Die bei Beendigung aufzurufende Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Adresse der vorherigen Funktion, die von bei Beendigung aufgerufen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Von der Funktion wird ein neues [terminate_handler](../standard-library/exception-typedefs.md#terminate_handler)-Element als die Funktion * `fnew` eingeführt. Daher darf `fnew` kein NULL-Zeiger sein. Die Funktion gibt die Adresse des vorherigen terminate-Handlers zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// exception_set_terminate.cpp  
// compile with: /EHsc  
#include <exception>  
#include <iostream>  
  
using namespace std;  
  
void termfunction()  
{  
    cout << "My terminate function called." << endl;  
    abort();  
}  
  
int main()  
{  
    terminate_handler oldHandler = set_terminate(termfunction);  
  
    // Throwing an unhandled exception would also terminate the program  
    // or we could explicitly call terminate();  
  
    //throw bad_alloc();  
    terminate();  
}  
  
```  
  
##  <a name="a-namegetunexpecteda--getunexpected"></a><a name="get_unexpected"></a> get_unexpected  
 Ruft die aktuelle `unexpected_handler`-Funktion ab.  
  
```cpp  
unexpected_handler get_unexpected();
```  
  
##  <a name="a-namesetunexpecteda--setunexpected"></a><a name="set_unexpected"></a> set_unexpected  
 Richtet ein neues `unexpected_handler` ein, das bei einer unerwarteten Ausnahme auftritt.  
  
```  
unexpected_handler set_unexpected(unexpected_handler fnew) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `fnew`  
 Die Funktion, die bei einer unerwarteten Ausnahme aufgerufen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Adresse des vorherigen `unexpected_handler`-Elements.  
  
### <a name="remarks"></a>Hinweise  
 `fnew` darf kein NULL-Zeiger sein.  
  
 Für den C++-Standard ist es erforderlich, dass `unexpected` aufgerufen wird, wenn eine Funktion eine Ausnahme auslöst, die nicht auf der Auslöseliste aufgeführt wird. Die augenblickliche Implementierung unterstützt das nicht. Im folgenden Beispiel ruft `unexpected` direkt auf, woraufhin `unexpected_handler` aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// exception_set_unexpected.cpp  
// compile with: /EHsc  
#include <exception>  
#include <iostream>  
  
using namespace std;  
  
void uefunction()  
{  
    cout << "My unhandled exception function called." << endl;  
    terminate(); // this is what unexpected() calls by default  
}  
  
int main()  
{  
    unexpected_handler oldHandler = set_unexpected(uefunction);  
  
    unexpected(); // library function to force calling the   
                  // current unexpected handler  
}  
  
```  
  
##  <a name="a-nameterminatea--terminate"></a><a name="terminate"></a> terminate  
 Ruft einen terminate-Handler auf.  
  
```  
void terminate();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion ruft einen terminate-Handler auf, eine Funktion vom Typ `void`. Wenn **terminate** direkt vom Programm aufgerufen wird, ist der terminate-Handler durch einen Aufruf von [set_terminate](../standard-library/exception-functions.md#set_terminate) der zuletzt festgelegte Handler. Wenn **terminate** aus einem von vielen weiteren Gründen während der Auswertung eines Throw-Ausdrucks aufgerufen wird, ist der terminate-Handler, der der direkt nach der Auswertung des Throw-Ausdrucks in Kraft ist.  
  
 Ein terminate-Handler kehrt möglicherweise nicht zum Aufrufer zurück. Bei Programmstart ist der terminate-Handler eine Funktion, die **abort** aufruft.  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel zur Verwendung von **terminate** finden Sie unter [set_unexpected](../standard-library/exception-functions.md#set_unexpected).  
  
##  <a name="a-nameuncaughtexceptiona--uncaughtexception"></a><a name="uncaught_exception"></a> uncaught_exception  
 Gibt nur dann `true` zurück, wenn augenblicklich eine Ausnahme verarbeitet wird.  
  
```  
bool uncaught_exception();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `true` nach Abschluss der Auswertung eines Throw-Ausdrucks und vor Abschluss der Initialisierung der Ausnahmedeklaration an den entsprechenden Handler oder durch Aufruf von [unexpected](../standard-library/exception-functions.md#unexpected) als Ergebnis des Throw-Ausdrucks zurück. Insbesondere gibt `uncaught_exception` `true` zurück, wenn die Funktion von einem Destruktor aufgerufen wird, der während des Entladevorgangs für die Ausnahme aufgerufen wird. Auf Geräten wird `uncaught_exception` nur auf Windows CE 5.00 und höheren Versionen, darunter Windows Mobile 2005-Plattformen unterstützt.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// exception_uncaught_exception.cpp  
// compile with: /EHsc  
#include <exception>  
#include <iostream>  
#include <string>  
  
class Test   
{  
public:  
   Test( std::string msg ) : m_msg( msg )   
   {  
      std::cout << "In Test::Test(\"" << m_msg << "\")" << std::endl;  
   }  
   ~Test( )   
   {  
      std::cout << "In Test::~Test(\"" << m_msg << "\")" << std::endl  
         << "        std::uncaught_exception( ) = "  
         << std::uncaught_exception( )  
         << std::endl;  
   }  
private:  
    std::string m_msg;  
};  
  
// uncaught_exception will be true in the destructor   
// for the object created inside the try block because   
// the destructor is being called as part of the unwind.  
  
int main( void )  
   {  
      Test t1( "outside try block" );  
      try   
      {  
         Test t2( "inside try block" );  
         throw 1;  
      }  
      catch (...) {  
   }  
}  
```  
  
```Output  
In Test::Test("outside try block")  
In Test::Test("inside try block")  
In Test::~Test("inside try block")  
        std::uncaught_exception( ) = 1  
In Test::~Test("outside try block")  
        std::uncaught_exception( ) = 0  
```  
  
##  <a name="a-nameunexpecteda--unexpected"></a><a name="unexpected"></a> unexpected  
 Ruft den unerwarteten Handler auf.  
  
```  
void unexpected();
```  
  
### <a name="remarks"></a>Hinweise  
 Für den C++-Standard ist es erforderlich, dass `unexpected` aufgerufen wird, wenn eine Funktion eine Ausnahme auslöst, die nicht auf der Auslöseliste aufgeführt wird. Die augenblickliche Implementierung unterstützt das nicht. Das Beispiel ruft `unexpected` direkt auf, wodurch der unerwartete Handler aufgerufen wird.  
  
 Die Funktion ruft einen unerwarteten Handler auf, eine Funktion vom Typ `void`. Wenn `unexpected` direkt vom Programm aufgerufen wird, ist der unerwartete Handler durch einen Aufruf von [set_unexpected](../standard-library/exception-functions.md#set_unexpected) der zuletzt festgelegte Handler.  
  
 Ein unerwarteter Handler kehrt möglicherweise nicht zum Aufrufer zurück. Die Ausführung kann hierdurch beendet werden:  
  
-   Auslösen eines Objekts eines Typs, das in der Ausnahmespezifikation gelistet ist oder eines Objekts jeglichen Typs, wenn der unerwartete Handler direkt durch das Programm aufgerufen wird.  
  
-   Auslösen eines Objekt des Typs [bad_exception](../standard-library/bad-exception-class.md).  
  
-   Aufrufen von [terminate](../standard-library/exception-functions.md#terminate), **abort** oder **exit** (`int`).  
  
 Bei Programmstart ist der unerwartete Handler eine Funktion, die [erminate](../standard-library/exception-functions.md#terminate) aufruft.  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel zur Verwendung von **unexpected** finden Sie unter [set_unexpected](../standard-library/exception-functions.md#set_unexpected).  
  
## <a name="see-also"></a>Siehe auch  
 [\<exception>](../standard-library/exception.md)


