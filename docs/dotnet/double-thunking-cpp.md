---
title: Doppeltes Thunking (C++) | Microsoft-Dokumentation
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
ms.openlocfilehash: 3e37b3b7fc477de0bdbeb00a15ebd86e6c44d25c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216636"
---
# <a name="double-thunking-c"></a>Doppeltes Thunking (C++)
Doppeltes thunking verweist, zum Verlust der Leistung, die auftreten können, wenn ein Funktionsaufruf in einen verwalteten kontextaufrufen, eine Visual C++ verwalteten Funktion und Ausführung des Programms, in dem systemeigenen Einstiegspunkt der Funktion aufruft, um eine verwaltete Funktion aufzurufen. In diesem Thema wird erläutert, in denen doppeltes thunking tritt auf, und wie Sie es zur Verbesserung der Leistung vermeiden können.  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig wird beim Kompilieren mit **"/ CLR"**, die Definition einer verwalteten Funktion bewirkt, dass den Compiler einen verwalteten Einstiegspunkt und einen einheitlichen Einstiegspunkt generiert. Dadurch wird die verwaltete Funktion, die von systemeigenen und verwalteten Aufrufsites aufgerufen werden. Wenn ein systemeigener Einstiegspunkt vorhanden ist, kann es jedoch den Einstiegspunkt für alle Aufrufe an die Funktion sein. Wenn es sich bei eine aufrufende Funktion verwaltet wird, wird in der systemeigenen Einstiegspunkt klicken Sie dann den verwalteten Einstiegspunkt aufgerufen. Aktiviert ist, sind zwei Aufrufe zum Aufrufen der Funktion erforderlich (daher doppelte thunking). Beispielsweise werden virtuelle Funktionen, die immer über einen systemeigener Einstiegspunkt aufgerufen.  
  
 Eine Lösung ist, um dem Compiler nicht, um einen systemeigener Einstiegspunkt für eine verwaltete Funktion zu generieren, die Funktion wird mit nur von einem verwalteten Kontext aufgerufen werden die [__clrcall](../cpp/clrcall.md) Aufrufkonvention.  
  
 Auf ähnliche Weise, wenn Sie exportieren ([Dllexport, Dllimport](../cpp/dllexport-dllimport.md)) eine verwaltete Funktion, ein systemeigener Einstiegspunkt wird generiert, und alle Funktionen, die importiert und ruft diese Funktion wird durch den systemeigenen Einstiegspunkt aufgerufen. Um doppeltes thunking in dieser Situation zu vermeiden, verwenden Sie keine Semantik für nativen exportieren/importieren. verweisen Sie einfach die Metadaten über `#using` (finden Sie unter [#using-Direktive](../preprocessor/hash-using-directive-cpp.md)).  
  
 Der Compiler wurde aktualisiert, um unnötige doppeltes thunking zu reduzieren. Z. B. eine beliebige Funktion mit einem verwalteten Typ in der Signatur (einschließlich Rückgabetyp) werden implizit als markiert `__clrcall`. Weitere Informationen zu doppelter Thunks, finden Sie unter [ https://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx ](https://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgende Beispiel wird veranschaulicht, doppeltes thunking. Bei systemeigener Kompilierung (ohne **"/ CLR"**), den Aufruf der virtuellen Funktion in `main` generiert einen Aufruf an `T`Konstruktor und einen Aufruf des Destruktors zu kopieren. Ein ähnliches Verhalten erfolgt, wenn die virtuelle Funktion deklariert wird, mit **"/ CLR"** und `__clrcall`. Allerdings bei der Kompilierung nur mit **"/ CLR"**, Aufruf der Funktion generiert einen Aufruf an den Copy-Konstruktor, aber es gibt einen weiteren Aufruf für den Kopierkonstruktor aufgrund der Thunk nativ zu verwaltet.  
  
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
 Im vorherigen Beispiel wurde das Vorhandensein des doppeltes thunking. Dieses Beispiel zeigt die Auswirkungen. Die `for` Schleife aufruft, die virtuelle Funktion und die Ausführungszeit der Programm-Berichte. Die längste Ausführungszeit wird gemeldet, wenn das Programm kompiliert wird, mit **"/ CLR"**. Die schnellste Ausführungszeiten werden gemeldet, beim Kompilieren ohne **"/ CLR"** oder wenn die virtuelle Funktion deklariert wird, mit `__clrcall`.  
  
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