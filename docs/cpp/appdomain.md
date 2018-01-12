---
title: AppDomain | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: appdomain_cpp
dev_langs: C++
helpviewer_keywords:
- appdomain __declspec keyword
- __declspec keyword [C++], appdomain
ms.assetid: 29d843cb-cb6b-4d1b-a48d-d928a877234d
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 677206e37cb4761112f66dc59dc44b2eccbabaf5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="appdomain"></a>appdomain
Gibt an, dass jede Anwendungsdomäne der verwalteten Anwendung eine eigene Kopie einer bestimmten globalen Variable oder statischen Membervariable haben soll. Finden Sie unter [Anwendungsdomänen und Visual C++](../dotnet/application-domains-and-visual-cpp.md) für Weitere Informationen.  
  
 Jede Anwendungsdomäne verfügt über eine eigene Kopie einer Anwendungsdomänenvariable. Ein Konstruktor einer Anwendungsdomänenvariable wird ausgeführt, wenn eine Assembly in eine Anwendungsdomäne geladen wird, und der Destruktor wird ausgeführt, wenn die Anwendungsdomäne entladen wird.  
  
 Wenn alle Anwendungsdomänen innerhalb eines Prozesses in der Common Language Runtime eine globale Variable gemeinsam nutzen sollen, verwenden Sie den `__declspec(process)`-Modifizierer. `__declspec(process)`ist wirksam standardmäßig unter ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) und `__declspec(appdomain)` ist wirksam standardmäßig unter **/CLR: pure**. `__declspec(appdomain)`wird unter erzwungen **/CLR: safe**. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 `__declspec(appdomain)`ist nur gültig, wenn eines der **"/ CLR"** -Compileroptionen verwendet wird. Nur eine globale Variable, eine statische Membervariable oder eine statische lokale Variable kann mit `__declspec(appdomain)` markiert werden. Es ist nicht zulässig, `__declspec(appdomain)` auf statische Member von verwalteten Typen anzuwenden, da diese immer dieses Verhalten aufweisen.  
  
 Mit `__declspec(appdomain)` ähnelt der Verwendung [Thread-lokalen Threadspeicher (TLS)](../parallel/thread-local-storage-tls.md). Threads verfügen über einen eigenen Speicher, genau wie Anwendungsdomänen. Die Verwendung `__declspec(appdomain)` stellt sicher, dass die globale Variable einen eigenen Speicher in jeder Anwendungsdomäne aufweist, die für die Anwendung erstellt wird.  
  
 Es gibt Einschränkungen beim Kombinieren der Verwendung von pro-Prozess und Appdomain-Variablen. finden Sie unter [Prozess](../cpp/process.md) für Weitere Informationen.  
  
 Beim Programmstart werden beispielsweise alle pro-Prozess-Variablen initialisiert, gefolgt von alle pro-AppDomain-Variablen. Wenn eine pro-Prozess-Variable initialisiert wird, kann sie also nicht vom Wert einer pro-AppDomain-Variablen abhängen. Es ist nicht üblich, die Verwendung (Zuweisung) der pro-Prozess- und pro-AppDomain-Variablen zu kombinieren.  
  
 Informationen zum Aufrufen einer Funktion in einer bestimmten Anwendungsdomäne finden Sie unter [Call_in_appdomain-Funktion](../dotnet/call-in-appdomain-function.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// declspec_appdomain.cpp  
// compile with: /clr  
#include <stdio.h>  
using namespace System;  
  
class CGlobal {  
public:  
   CGlobal(bool bProcess) {  
      Counter = 10;  
      m_bProcess = bProcess;  
      Console::WriteLine("__declspec({0}) CGlobal::CGlobal constructor", m_bProcess ? (String^)"process" : (String^)"appdomain");  
   }  
  
   ~CGlobal() {  
      Console::WriteLine("__declspec({0}) CGlobal::~CGlobal destructor", m_bProcess ? (String^)"process" : (String^)"appdomain");  
   }  
  
   int Counter;  
  
private:  
   bool m_bProcess;  
};  
  
__declspec(process) CGlobal process_global = CGlobal(true);  
__declspec(appdomain) CGlobal appdomain_global = CGlobal(false);  
  
value class Functions {  
public:  
   static void change() {  
      ++appdomain_global.Counter;  
   }  
  
   static void display() {  
      Console::WriteLine("process_global value in appdomain '{0}': {1}",   
         AppDomain::CurrentDomain->FriendlyName,  
         process_global.Counter);  
  
      Console::WriteLine("appdomain_global value in appdomain '{0}': {1}",   
         AppDomain::CurrentDomain->FriendlyName,  
         appdomain_global.Counter);  
   }  
};  
  
int main() {  
   AppDomain^ defaultDomain = AppDomain::CurrentDomain;  
   AppDomain^ domain = AppDomain::CreateDomain("Domain 1");  
   AppDomain^ domain2 = AppDomain::CreateDomain("Domain 2");  
   CrossAppDomainDelegate^ changeDelegate = gcnew CrossAppDomainDelegate(&Functions::change);  
   CrossAppDomainDelegate^ displayDelegate = gcnew CrossAppDomainDelegate(&Functions::display);  
  
   // Print the initial values of appdomain_global in all appdomains.  
   Console::WriteLine("Initial value");  
   defaultDomain->DoCallBack(displayDelegate);  
   domain->DoCallBack(displayDelegate);  
   domain2->DoCallBack(displayDelegate);  
  
   // Changing the value of appdomain_global in the domain and domain2  
   // appdomain_global value in "default" appdomain remain unchanged  
   process_global.Counter = 20;  
   domain->DoCallBack(changeDelegate);  
   domain2->DoCallBack(changeDelegate);  
   domain2->DoCallBack(changeDelegate);  
  
   // Print values again  
   Console::WriteLine("Changed value");  
   defaultDomain->DoCallBack(displayDelegate);  
   domain->DoCallBack(displayDelegate);  
   domain2->DoCallBack(displayDelegate);  
  
   AppDomain::Unload(domain);  
   AppDomain::Unload(domain2);  
}  
```  
  
```Output  
__declspec(process) CGlobal::CGlobal constructor  
__declspec(appdomain) CGlobal::CGlobal constructor  
Initial value  
process_global value in appdomain 'declspec_appdomain.exe': 10  
appdomain_global value in appdomain 'declspec_appdomain.exe': 10  
__declspec(appdomain) CGlobal::CGlobal constructor  
process_global value in appdomain 'Domain 1': 10  
appdomain_global value in appdomain 'Domain 1': 10  
__declspec(appdomain) CGlobal::CGlobal constructor  
process_global value in appdomain 'Domain 2': 10  
appdomain_global value in appdomain 'Domain 2': 10  
Changed value  
process_global value in appdomain 'declspec_appdomain.exe': 20  
appdomain_global value in appdomain 'declspec_appdomain.exe': 10  
process_global value in appdomain 'Domain 1': 20  
appdomain_global value in appdomain 'Domain 1': 11  
process_global value in appdomain 'Domain 2': 20  
appdomain_global value in appdomain 'Domain 2': 12  
__declspec(appdomain) CGlobal::~CGlobal destructor  
__declspec(appdomain) CGlobal::~CGlobal destructor  
__declspec(appdomain) CGlobal::~CGlobal destructor  
__declspec(process) CGlobal::~CGlobal destructor  
```  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)