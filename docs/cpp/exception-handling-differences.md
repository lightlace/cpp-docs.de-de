---
title: "Unterschiede für die Ausnahmebehandlung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 63fff00222aa083bcb392e0d71411bfcf5c0f418
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exception-handling-differences"></a>Unterschiede bei der Ausnahmebehandlung
Der Hauptunterschied zwischen einer strukturierten Ausnahmebehandlung und einer C++-Ausnahmebehandlung besteht darin, dass das C++-Ausnahmebehandlungsmodell Typen behandelt, während das Modell der C-strukturierten Ausnahmebehandlung mit Ausnahmen eines Typen arbeitet, insbesondere `unsigned int`. Das bedeutet, dass C-Ausnahmen über einen Ganzzahlwert ohne Vorzeichen identifiziert werden und C++-Ausnahmen über den Datentyp. Wenn in C eine Ausnahme ausgelöst wird, führt jeder mögliche Handler einen Filter aus, der den C-Ausnahmekontext validiert und bestimmt, ob die Ausnahme akzeptiert, an einen anderen Handler übergeben oder ignoriert wird. Wenn eine Ausnahme in C++ ausgelöst wird, kann sie einem beliebigen Typ angehören.  
  
 Ein zweiter Unterschied besteht darin, dass das Modell C-strukturierter Ausnahmebehandlung als das so genannte "asynchrone" bezeichnet wird, in dem Ausnahmen sekundär zum normalen Programmablauf auftreten. Der C++-Ausnahmebehandlungsmechanismus ist vollständig „synchron“, was bedeutet, dass Ausnahmen nur auftreten, wenn sie ausgelöst werden.  
  
 Wenn in einem C++-Programm eine C-Ausnahme ausgelöst wird, es kann verarbeitet werden von einem strukturierten Ausnahmehandler mit dem zugeordneten Filter oder einem C++ **catch** Handler, welcher Wert ist dynamisch dem Ausnahmekontext. Das folgende C++-Programm löst z. B. eine C-Ausnahme innerhalb eines C++ **versuchen** Kontext:  
  
## <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="_core_c_exception_wrapper_class"></a>C-Ausnahme-Wrapperklasse  
 In einem einfachen Beispiel wie oben, die C-Ausnahme abgefangen werden kann, nur durch ein Auslassungszeichen (**...** ) **catch** Handler. Es werden keine Informationen über den Typ oder die Art der Ausnahme an den Handler übermittelt. Diese Methode funktioniert zwar, in einigen Fällen müssen Sie jedoch u. U. eine Transformation zwischen den beiden Ausnahmebehandlungsmodellen definieren, damit jede C-Ausnahme einer bestimmten Klasse zugeordnet wird. Dazu können Sie eine Wrapperklasse für eine C-Ausnahme definieren, die verwendet oder abgeleitet werden kann, um einer C-Ausnahme einen speziellen Klassentyp zuzuordnen. Auf diese Weise kann jede C-Ausnahme vom C++ behandelt werden **catch** Handler mehr separat als in vorherigen Beispiel.  
  
 Die Wrapperklasse enthält eventuell eine Schnittstelle, die aus mehreren Memberfunktionen besteht, die den Wert der Ausnahme bestimmen und auf die erweiterten Ausnahmekontextinformationen zugreifen, die vom C-Ausnahmemodell bereitgestellt werden. Sie können auch einen Standardkonstruktor und einen Konstruktor definieren, der ein `unsigned int`-Argument akzeptiert (um die zugrunde liegende C-Ausnahme-Darstellung bereitzustellen), und einen Konstruktor für bitweise Kopien. Es folgt eine mögliche Implementierung einer C-Ausnahme-Wrapperklasse:  
  
```  
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
  
 Um diese Klasse zu verwenden, installieren Sie eine benutzerdefinierte C-Ausnahmeübersetzungsfunktion, die bei jedem Auslösen einer C-Ausnahme vom internen Mechanismus für die Ausnahmebehandlung aufgerufen wird. In der Übersetzungsfunktion können Sie eine beliebige typisierte Ausnahme auslösen (vielleicht ein `SE_Exception` Typ oder einen Klassentyp abgeleitete `SE_Exception`), die abgefangen werden kann, von einem entsprechenden übereinstimmenden C++ **catch** Handler. Die Übersetzungsfunktion kann einfach zurückkehren. Sie hat also die Ausnahme nicht bearbeitet. Wenn die Übersetzungsfunktion selbst eine C-Ausnahme auslöst [beenden](../c-runtime-library/reference/terminate-crt.md) aufgerufen wird.  
  
 Um eine benutzerdefinierte Übersetzungsfunktion anzugeben, rufen die [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) Funktion mit dem Namen Ihrer Übersetzungsfunktion als einziges Argument. Die Übersetzungsfunktion, die Sie schreiben wird einmal für jeden Funktionsaufruf im Stapel mit aufgerufen **versuchen** blockiert. Es ist keine Funktion. Wenn Sie nicht durch den Aufruf angeben `_set_se_translator`, die C-Ausnahme kann nur durch Ellipsen abgefangen werden **catch** Handler.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code installiert beispielsweise eine benutzerdefinierte Übersetzungsfunktion und löst anschließend eine C-Ausnahme aus, die von der `SE_Exception`-Klasse umschlossen wird:  
  
```  
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
 [Kombination von C (strukturiert)- und C++-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)