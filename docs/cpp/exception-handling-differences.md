---
title: "Unterschiede bei der Ausnahmebehandlung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++-Ausnahmebehandlung, Im Vergleich zu strukturierter Ausnahmebehandlung"
  - "Ausnahmen, Wrapperklasse"
  - "Strukturierte Ausnahmebehandlung, Im Vergleich zu C++-Ausnahmebehandlung"
  - "Strukturierte Ausnahmebehandlung, Im Vergleich zu unstrukturiert"
  - "Wrapperklassen, C-Ausnahme"
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Unterschiede bei der Ausnahmebehandlung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Hauptunterschied zwischen einer strukturierten Ausnahmebehandlung und einer C\+\+\-Ausnahmebehandlung besteht darin, dass das C\+\+\-Ausnahmebehandlungsmodell Typen behandelt, während das Modell der C\-strukturierten Ausnahmebehandlung mit Ausnahmen eines Typen arbeitet, insbesondere `unsigned int`.  Das bedeutet, dass C\-Ausnahmen über einen Ganzzahlwert ohne Vorzeichen identifiziert werden und C\+\+\-Ausnahmen über den Datentyp.  Wenn in C eine Ausnahme ausgelöst wird, führt jeder mögliche Handler einen Filter aus, der den C\-Ausnahmekontext validiert und bestimmt, ob die Ausnahme akzeptiert, an einen anderen Handler übergeben oder ignoriert wird.  Wenn eine Ausnahme in C\+\+ ausgelöst wird, kann sie einem beliebigen Typ angehören.  
  
 Ein zweiter Unterschied besteht darin, dass das Modell C\-strukturierter Ausnahmebehandlung als das so genannte "asynchrone" bezeichnet wird, in dem Ausnahmen sekundär zum normalen Programmablauf auftreten.  Der C\+\+\-Ausnahmebehandlungsmechanismus ist vollständig "synchron", was bedeutet, dass Ausnahmen nur auftreten, wenn sie ausgelöst werden.  
  
 Wenn eine C\-Ausnahme in einem C\+\+\-Programm ausgelöst wird, kann sie von einem strukturierten Ausnahmehandler mit dem zugeordneten Filter oder einem C\+\+\-**catch**\-Handler behandelt werden, je nachdem, welcher Handler dem Ausnahmekontext dynamisch näher ist.  Zum Beispiel löst das folgende C\+\+\-Programm eine C\-Ausnahme innerhalb eines C\+\+\-**try**\-Kontexts aus:  
  
## Beispiel  
  
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
  
  **In finally.**  
**Caught a C exception.**   
##  <a name="_core_c_exception_wrapper_class"></a> C\-Ausnahme\-Wrapperklasse  
 In einem einfachen Beispiel wie oben kann die C\-Ausnahme nur von einem **catch**\-Handler für das Auslassungszeichen \(**...**\) abgefangen werden.  Es werden keine Informationen über den Typ oder die Art der Ausnahme an den Handler übermittelt.  Diese Methode funktioniert zwar, in einigen Fällen müssen Sie jedoch u. U. eine Transformation zwischen den beiden Ausnahmebehandlungsmodellen definieren, damit jede C\-Ausnahme einer bestimmten Klasse zugeordnet wird.  Dazu können Sie eine Wrapperklasse für eine C\-Ausnahme definieren, die verwendet oder abgeleitet werden kann, um einer C\-Ausnahme einen speziellen Klassentyp zuzuordnen.  Dadurch kann jede C\-Ausnahme vom C\+\+\-**catch**\-Handler separater behandelt werden, als im vorhergehenden Beispiel.  
  
 Die Wrapperklasse enthält eventuell eine Schnittstelle, die aus mehreren Memberfunktionen besteht, die den Wert der Ausnahme bestimmen und auf die erweiterten Ausnahmekontextinformationen zugreifen, die vom C\-Ausnahmemodell bereitgestellt werden.  Sie können auch einen Standardkonstruktor und einen Konstruktor definieren, der ein `unsigned int`\-Argument akzeptiert \(um die zugrunde liegende C\-Ausnahme\-Darstellung bereitzustellen\), und einen Konstruktor für bitweise Kopien.  Es folgt eine mögliche Implementierung einer C\-Ausnahme\-Wrapperklasse:  
  
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
  
 Um diese Klasse zu verwenden, installieren Sie eine benutzerdefinierte C\-Ausnahmeübersetzungsfunktion, die bei jedem Auslösen einer C\-Ausnahme vom internen Mechanismus für die Ausnahmebehandlung aufgerufen wird.  In der Übersetzungsfunktion können Sie eine beliebige typisierte Ausnahme auslösen \(u. U. einen `SE_Exception`\-Typ oder einen von `SE_Exception` abgeleiteten Klassentyp\), die von einem entsprechenden übereinstimmenden C\+\+\-**catch**\-Handler abgefangen werden kann.  Die Übersetzungsfunktion kann einfach zurückkehren. Sie hat also die Ausnahme nicht bearbeitet.  Wenn die Übersetzungsfunktion selbst eine C\-Ausnahme auslöst, wird [terminate](../c-runtime-library/reference/terminate-crt.md) aufgerufen.  
  
 Um eine benutzerdefinierte Übersetzungsfunktion anzugeben, rufen Sie die [\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md)\-Funktion mit dem Namen Ihrer Übersetzungsfunktion als einziges Argument auf.  Die Übersetzungsfunktion, die Sie schreiben, wird einmal für jeden Funktionsaufruf im Stapel mit **try**\-Blöcken aufgerufen.  Eine Standardübersetzungsfunktion ist nicht vorhanden. Wenn Sie keine Funktion durch Aufrufen von `_set_se_translator` angeben, kann die C\-Ausnahme nur durch einen **catch**\-Handler für das Auslassungszeichen aufgefangen werden.  
  
## Beispiel  
 Der folgende Code installiert beispielsweise eine benutzerdefinierte Übersetzungsfunktion und löst anschließend eine C\-Ausnahme aus, die von der `SE_Exception`\-Klasse umschlossen wird:  
  
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
  
  **In trans\_func.**  
**In finally**  
**Caught a \_\_try exception with SE\_Exception.**  
**nSE \= 0xc0000094**   
## Siehe auch  
 [Kombination von C \(strukturiert\)\- und C\+\+\-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)