---
title: "Doppeltes Thunking (C++)"
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
  - "/clr-Compileroption [C++], Doppeltes Thunking"
  - "Doppelthunks"
  - "Interop [C++], Doppeltes Thunking"
  - "Interoperabilität [C++], Doppeltes Thunking"
  - "Gemischte Assemblys [C++], Doppeltes Thunking"
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Doppeltes Thunking (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Doppeltes Thunking bezieht sich auf den Leistungsabfall, wenn ein Funktionsaufruf in einem verwalteten Kontext eine verwaltete Visual C\+\+\-Funktion aufruft und die Programmausführung den systemeigenen Einstiegspunkt der Funktion zum Aufrufen der verwalteten Funktion aufruft.  In diesem Thema wird erläutert, wo doppeltes Thunking auftritt und wie Sie es zur Verbesserung der Leistung vermeiden können.  
  
## Hinweise  
 Standardmäßig veranlasst die Definition einer verwalteten Funktion beim Kompilieren mit **\/clr** \(nicht **\/clr:pure**\) den Compiler, einen verwalteten und einen systemeigenen Einstiegspunkt zu generieren.  Dadurch kann die verwaltete Funktion von systemeigenen und verwalteten Aufrufsites aus aufgerufen werden.  Wenn allerdings ein systemeigener Einstiegspunkt vorhanden ist, kann er für alle Aufrufe der Funktion verwendet werden.  Wenn die aufrufende Funktion eine verwaltete ist, ruft der systemeigene Einstiegspunkt den verwalteten Einstiegspunkt auf.  Praktisch sind zwei Aufrufe erforderlich, um die Funktion aufzurufen \(also ein doppelter Thunk\).  Virtuelle Funktionen werden beispielsweise immer über einen systemeigenen Einstiegspunkt aufgerufen.  
  
 Eine Möglichkeit besteht darin, dem Compiler mitzuteilen, dass er keinen systemeigenen Einstiegspunkt für eine verwaltete Funktion generieren soll, sodass die Funktion aus einem verwalteten Kontext heraus nur mit der [\_\_clrcall](../cpp/clrcall.md)\-Aufrufkonvention aufgerufen wird.  
  
 In ähnlicher Weise wird ein systemeigener Einstiegspunkt generiert, wenn Sie eine verwaltete Funktion exportieren \([dllexport, dllimport](../cpp/dllexport-dllimport.md)\). Jede Funktion, die diese Funktion importiert und aufruft, verwendet dafür den systemeigenen Einstiegspunkt.  Um in dieser Situation doppeltes Thunking zu vermeiden, verwenden Sie nicht die systemeigene Export\/Import\-Semantik; verweisen Sie einfach über `#using` auf die Metadaten \(Informationen dazu finden Sie unter [\#using\-Direktive](../preprocessor/hash-using-directive-cpp.md)\).  
  
 Der Compiler wurde aktualisiert, um unnötiges doppeltes Thunking zu reduzieren.  Beispielsweise wird jede Funktion mit einem verwalteten Typ in der Signatur \(einschließlich Rückgabetypen\) implizit als `__clrcall` gekennzeichnet.  Weitere Informationen über doppelte Thunkbeseitigung, Sie finden [http:\/\/msdn.microsoft.com\/msdnmag\/issues\/05\/01\/COptimizations\/default.aspx](http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx).  
  
## Beispiel  
  
### **Beschreibung**  
 Im folgenden Beispiel wird doppeltes Thunking veranschaulicht.  Bei systemeigener Kompilierung \(ohne **\/clr**\) generiert der Aufruf der virtuellen Funktion in `main` einen Aufruf an den Kopierkonstruktor von `T` und einen an den Destruktor.  Ein ähnliches Verhalten wird erreicht, wenn die virtuelle Funktion mit **\/clr** und `__clrcall` deklariert wird.  Wenn jedoch nur mit **\/clr** kompiliert wird, generiert der Funktionsaufruf einen Aufruf an den Kopierkonstruktor, wobei wegen des Thunks bei Aufruf von verwaltetem durch systemeigenen Code ein weiterer Aufruf an den Kopierkonstruktor erfolgt.  
  
### Code  
  
```  
// double_thunking.cpp  
// compile with: /clr  
#include <stdio.h>  
struct T {  
   T() {  
      puts(__FUNCSIG__);  
   }  
  
   T(const T&) {  
      puts(__FUNCSIG__);  
   }  
  
   ~T() {  
      puts(__FUNCSIG__);  
   }  
  
   T& operator=(const T&) {  
      puts(__FUNCSIG__);  
      return *this;  
   }  
};  
  
struct S {  
   virtual void /* __clrcall */ f(T t) {};  
} s;  
  
int main() {  
   S* pS = &s;  
   T t;  
  
   printf("calling struct S\n");  
   pS->f(t);  
   printf("after calling struct S\n");  
}  
```  
  
### Beispielausgabe  
  
```  
__thiscall T::T(void)  
calling struct S  
__thiscall T::T(const struct T &)  
__thiscall T::T(const struct T &)  
__thiscall T::~T(void)  
__thiscall T::~T(void)  
after calling struct S  
__thiscall T::~T(void)  
```  
  
## Beispiel  
  
### **Beschreibung**  
 Im vorherigen Beispiel wurde das doppelte Thunking veranschaulicht.  In diesem Beispiel wird seine Wirkung veranschaulicht.  Die `for`\-Schleife ruft die virtuelle Funktion auf, und das Programm meldet die Ausführungszeit.  Die längste Ausführungszeit wird gemeldet, wenn das Programm mit **\/clr** kompiliert wird.  Die kürzesten Ausführungszeiten werden gemeldet, wenn ohne **\/clr** kompiliert wird oder die virtuelle Funktion mit `__clrcall` deklariert wird.  
  
### Code  
  
```  
// double_thunking_2.cpp  
// compile with: /clr  
#include <time.h>  
#include <stdio.h>   
  
#pragma unmanaged  
struct T {  
   T() {}  
   T(const T&) {}  
   ~T() {}  
   T& operator=(const T&) { return *this; }  
};  
  
struct S {  
   virtual void /* __clrcall */ f(T t) {};  
} s;  
  
int main() {  
   S* pS = &s;  
   T t;  
   clock_t start, finish;  
   double  duration;  
   start = clock();  
  
   for ( int i = 0 ; i < 1000000 ; i++ )  
      pS->f(t);  
  
   finish = clock();  
   duration = (double)(finish - start) / (CLOCKS_PER_SEC);  
   printf( "%2.1f seconds\n", duration );  
   printf("after calling struct S\n");  
}  
```  
  
### Beispielausgabe  
  
```  
4.2 seconds  
after calling struct S  
```  
  
## Siehe auch  
 [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)