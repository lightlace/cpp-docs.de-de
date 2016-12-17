---
title: "Unterschiede im Ausnahmebehandlungsverhalten unter /CLR"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EXCEPTION_CONTINUE_EXECUTION-Makro"
  - "set_se_translator-Funktion"
ms.assetid: 2e7e8daf-d019-44b0-a51c-62d7aaa89104
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# Unterschiede im Ausnahmebehandlungsverhalten unter /CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Grundlegende Konzepte, wenn verwaltete Ausnahmen verwendet werden](../dotnet/basic-concepts-in-using-managed-exceptions.md) erläutert Ausnahmebehandlung in verwalteten Anwendungen.  In diesem Thema werden Unterschiede zum Standardverhalten der Ausnahmebehandlung und einige Einschränkungen im Detail erläutert.  Weitere Informationen finden Sie unter [Die \_set\_se\_translator Funktion](../c-runtime-library/reference/set-se-translator.md).  
  
##  <a name="vcconjumpingoutofafinallyblock"></a> Herausspringen eines Finally\-Blocks  
 In systemeigenen C\/C\+\+\-Code wird das Herausspringen eines **finally**\-Blocks mit der strukturierten Ausnahmebehandlung \(SEH\) zulässig, obwohl eine Warnung generiert.  Gemäß [\/clr](../build/reference/clr-common-language-runtime-compilation.md) führt das Herausspringen eines **finally**\-Blocks einen Fehler:  
  
```  
// clr_exception_handling_4.cpp  
// compile with: /clr  
int main() {  
   try {}  
   finally {  
      return 0;   // also fails with goto, break, continue  
    }  
}   // C3276  
```  
  
##  <a name="vcconraisingexceptionswithinanexceptionfilter"></a> Auslösen von Ausnahmen in einem Ausnahme\-Filters  
 Wenn eine Ausnahme während der Verarbeitung von [Ausnahmefilter](../cpp/writing-an-exception-filter.md) innerhalb des verwalteten Codes ausgelöst wird, wird die Ausnahme als ob die Filterrückgaben 0 abgefangen und behandelt.  
  
 Im Gegensatz zu dem Verhalten im systemeigenen Code, in dem eine geschachtelte Ausnahme ausgelöst wird, das Feld **ExceptionRecord** in der **EXCEPTION\_RECORD**\-Struktur \(z von [GetExceptionInformation](http://msdn.microsoft.com/library/windows/desktop/ms679357) zurückgegeben\) wird festgelegt und die **ExceptionFlags** Feldsätze das Bit 0x10.  Das folgende Beispiel veranschaulicht diesen Unterschied des Verhaltens:  
  
```  
// clr_exception_handling_5.cpp  
#include <windows.h>  
#include <stdio.h>  
#include <assert.h>  
  
#ifndef false  
#define false 0  
#endif  
  
int *p;  
  
int filter(PEXCEPTION_POINTERS ExceptionPointers) {  
   PEXCEPTION_RECORD ExceptionRecord =   
                     ExceptionPointers->ExceptionRecord;  
  
   if ((ExceptionRecord->ExceptionFlags & 0x10) == 0) {  
      // not a nested exception, throw one  
      *p = 0; // throw another AV  
   }  
   else {  
      printf("Caught a nested exception\n");  
      return 1;  
    }  
  
   assert(false);  
  
   return 0;  
}  
  
void f(void) {  
   __try {  
      *p = 0;   // throw an AV  
   }  
   __except(filter(GetExceptionInformation())) {  
      printf_s("We should execute this handler if "  
                 "compiled to native\n");  
    }  
}  
  
int main() {  
   __try {  
      f();  
   }  
   __except(1) {  
      printf_s("The handler in main caught the "  
               "exception\n");  
    }  
}  
```  
  
### Ausgabe  
  
```  
Caught a nested exception  
We should execute this handler if compiled to native  
```  
  
##  <a name="vccondisassociatedrethrows"></a> Die Eigenschaft löst erneut aus  
 **\/clr** unterstützt keine erneute Auslösen einer Ausnahme außerhalb eines catch\-Handlers \(ist die Zuordnung nicht lösen Sie erneut aus\).  Ausnahmen dieses Typs werden behandelt, während Standard\-C\+\+ erneut auslösen.  Wenn die Zuordnung nicht auftritt erneut auslösen, wenn eine aktive verwaltete Ausnahme gibt, wird die Ausnahme als eine C\+\+\-Ausnahme umschlossen und dann erneut ausgelöst.  Ausnahmen dieses Typs können als Ausnahme des Typs [System::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx) nur abgefangen werden.  
  
 Das folgende Beispiel zeigt eine verwaltete Ausnahme, die als eine C\+\+\-Ausnahme erneut ausgelöst wird:  
  
```  
// clr_exception_handling_6.cpp  
// compile with: /clr  
using namespace System;  
#include <assert.h>  
#include <stdio.h>  
  
void rethrow( void ) {  
   // This rethrow is a dissasociated rethrow.  
   // The exception would be masked as SEHException.  
   throw;  
}  
  
int main() {  
   try {  
      try {  
         throw gcnew ApplicationException;  
      }  
      catch ( ApplicationException^ ) {  
         rethrow();  
         // If the call to rethrow() is replaced with  
         // a throw statement within the catch handler,  
         // the rethrow would be a managed rethrow and  
         // the exception type would remain   
         // System::ApplicationException  
      }  
   }  
  
    catch ( ApplicationException^ ) {  
      assert( false );  
  
      // This will not be executed since the exception  
      // will be masked as SEHException.  
    }  
   catch ( Runtime::InteropServices::SEHException^ ) {  
      printf_s("caught an SEH Exception\n" );  
    }  
}  
```  
  
### Ausgabe  
  
```  
caught an SEH Exception  
```  
  
##  <a name="vcconexceptionfiltersandexception_continue_execution"></a> Ausnahme\-Filter und EXCEPTION\_CONTINUE\_EXECUTION  
 Wenn ein Filter `EXCEPTION_CONTINUE_EXECUTION` in einer verwalteten Anwendung zurückgibt, wird er behandelt, als ob der Filter `EXCEPTION_CONTINUE_SEARCH` zurückgibt.  Weitere Informationen über diese Konstanten, finden Sie unter [try\-except\-Anweisung](../cpp/try-except-statement.md).  
  
 Das folgende Beispiel veranschaulicht diesen Unterschied:  
  
```  
// clr_exception_handling_7.cpp  
#include <windows.h>  
#include <stdio.h>  
#include <assert.h>  
  
int main() {  
   int Counter = 0;  
   __try {  
      __try  {  
         Counter -= 1;  
         RaiseException (0xe0000000|'seh',  
                         0, 0, 0);  
         Counter -= 2;  
      }  
      __except (Counter) {  
         // Counter is negative,  
         // indicating "CONTINUE EXECUTE"  
         Counter -= 1;  
      }  
    }  
    __except(1) {  
      Counter -= 100;  
   }  
  
   printf_s("Counter=%d\n", Counter);  
}  
```  
  
### Ausgabe  
  
```  
Counter=-3  
```  
  
##  <a name="vcconthe_set_se_translatorfunction"></a> Die \_set\_se\_translator Funktion  
 Die Übersetzerfunktion, von einen Aufruf an `_set_se_translator`, der beeinflusst Erfassungen nur in nicht verwaltetem Code.  Im folgenden Beispiel wird diese Einschränkung:  
  
```  
// clr_exception_handling_8.cpp  
// compile with: /clr /EHa  
#include <iostream>  
#include <windows.h>  
#include <eh.h>  
#pragma warning (disable: 4101)  
using namespace std;  
using namespace System;  
  
#define MYEXCEPTION_CODE 0xe0000101  
  
class CMyException {  
public:  
   unsigned int m_ErrorCode;  
   EXCEPTION_POINTERS * m_pExp;  
  
   CMyException() : m_ErrorCode( 0 ), m_pExp( NULL ) {}  
  
   CMyException( unsigned int i, EXCEPTION_POINTERS * pExp )  
         : m_ErrorCode( i ), m_pExp( pExp ) {}  
  
   CMyException( CMyException& c ) : m_ErrorCode( c.m_ErrorCode ),  
                                      m_pExp( c.m_pExp ) {}  
  
   friend ostream& operator <<   
                 ( ostream& out, const CMyException& inst ) {  
      return out <<  "CMyException[\n" <<    
             "Error Code: " << inst.m_ErrorCode <<  "]";  
    }  
};  
  
#pragma unmanaged   
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS pExp ) {  
   cout <<  "In my_trans_func.\n";  
   throw CMyException( u, pExp );  
}  
  
#pragma managed   
void managed_func() {  
   try  {  
      RaiseException( MYEXCEPTION_CODE, 0, 0, 0 );  
   }  
   catch ( CMyException x ) {}  
   catch ( ... ) {  
      printf_s("This is invoked since "  
               "_set_se_translator is not "  
               "supported when /clr is used\n" );  
    }  
}  
  
#pragma unmanaged   
void unmanaged_func() {  
   try  {  
      RaiseException( MYEXCEPTION_CODE,   
                      0, 0, 0 );  
   }  
   catch ( CMyException x ) {  
      printf("Caught an SEH exception with "  
             "exception code: %x\n", x.m_ErrorCode );  
    }  
    catch ( ... ) {}  
}  
  
// #pragma managed   
int main( int argc, char ** argv ) {  
   _set_se_translator( my_trans_func );  
  
   // It does not matter whether the translator function  
   // is registered in managed or unmanaged code  
   managed_func();  
   unmanaged_func();  
}  
```  
  
### Ausgabe  
  
```  
This is invoked since _set_se_translator is not supported when /clr is used  
In my_trans_func.  
Caught an SEH exception with exception code: e0000101  
```  
  
## Siehe auch  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)   
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)