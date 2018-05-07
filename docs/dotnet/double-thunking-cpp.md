---
title: Doppeltes Thunking (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- double thunks
- interop [C++], double thunking
- mixed assemblies [C++], double thunking
- /clr compiler option [C++], double thunking
- interoperability [C++], double thunking
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 47d5bbbecc8e1b9743c543a503df1a0afa0dc0ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="double-thunking-c"></a>Doppeltes Thunking (C++)
Doppeltes thunking bezieht sich auf einen Datenverlust auf der Leistung, die auftreten können, wenn ein Funktionsaufruf in einen verwalteten Kontext aufrufen, die eine Visual C++-Funktion verwaltet und, in dem programmausführung systemeigener Einstiegspunkt der Funktion aufruft, um die verwaltete Funktion aufzurufen. In diesem Thema wird erläutert, wo doppeltes thunking auftritt und wie Sie es zur Verbesserung der Leistung vermeiden können.  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig wird beim Kompilieren mit **"/ CLR"**, die Definition einer verwalteten Funktion bewirkt, dass den Compiler einen verwalteten Einstiegspunkt und einen systemeigener Einstiegspunkt generiert. Dadurch wird die verwaltete Funktion von systemeigenen und verwalteten Aufrufsites aufgerufen werden soll. Wenn ein systemeigener Einstiegspunkt vorhanden ist, können sie den Einstiegspunkt für alle Aufrufe an die Funktion sein. Wenn es sich bei eine aufrufende Funktion verwaltet wird, wird der systemeigenen Einstiegspunkt klicken Sie dann den verwalteten Einstiegspunkt aufgerufen. Tatsächlich sind zwei Aufrufe zum Aufrufen der Funktion erforderlich (also ein doppelter Thunk). Virtuelle Funktionen sind z. B. immer über ein systemeigener Einstiegspunkt aufgerufen.  
  
 Eine Lösung ist, die der Compiler nicht, um ein systemeigener Einstiegspunkt für eine verwaltete Funktion generieren mitzuteilen, dass die Funktion wird mit nur aus einem verwalteten Kontext aufgerufen werden der [__clrcall](../cpp/clrcall.md) Aufrufkonvention.  
  
 Auf ähnliche Weise, wenn Sie exportieren ([Dllexport, Dllimport](../cpp/dllexport-dllimport.md)) eine verwaltete Funktion, ein systemeigener Einstiegspunkt wird generiert, und alle Funktionen, die importiert und ruft diese Funktion wird über den systemeigenen Einstiegspunkt aufgerufen. Um doppeltes thunking in dieser Situation zu vermeiden, verwenden Sie keine systemeigene mittels Export/Import-Semantik. verweisen Sie einfach die Metadaten über `#using` (siehe [#using-Direktive](../preprocessor/hash-using-directive-cpp.md)).  
  
 Der Compiler wurde aktualisiert, um unnötige doppeltes thunking zu reduzieren. Beispielsweise jede Funktion mit einem verwalteten Typ in der Signatur (einschließlich Rückgabetyp) werden implizit als markiert `__clrcall`. Weitere Informationen zu doppeltes Thunk für Eliminierung von Duplikaten, finden Sie unter [ http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx ](http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgende Beispiel wird veranschaulicht, doppeltes thunking. Bei der systemeigenen Kompilierung (ohne **"/ CLR"**), der Aufruf der virtuellen Funktion in `main` generiert einen Aufruf von `T`Konstruktor und einem Aufruf des Destruktors kopieren. Ein ähnliches Verhalten wird erreicht, wenn die virtuelle Funktion deklariert wird, mit **"/ CLR"** und `__clrcall`. Allerdings bei der Kompilierung nur mit **"/ CLR"** Funktionsaufruf generiert einen Aufruf für den Kopierkonstruktor, aber es gibt einen weiteren Aufruf für den Kopierkonstruktor aufgrund der Thunk systemeigen verwaltet.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="sample-output"></a>Beispielausgabe  
  
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
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im vorherigen Beispiel veranschaulicht das Vorhandensein des doppeltes thunking. In diesem Beispiel wird gezeigt, seiner Wirkung. Die `for` -Schleife Ruft die virtuelle Funktion und die Ausführungszeit der Programm-Berichte. Die längste Ausführungszeit wird gemeldet, wenn das Programm kompiliert wird, mit **"/ CLR"**. Die schnellsten Ausführungszeiten werden gemeldet, beim Kompilieren ohne **"/ CLR"** oder wenn die virtuelle Funktion deklariert wird, mit `__clrcall`.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="sample-output"></a>Beispielausgabe  
  
```  
4.2 seconds  
after calling struct S  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)