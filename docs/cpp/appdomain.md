---
title: "appdomain"
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
  - "appdomain_cpp"
  - "appdomain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], appdomain"
  - "appdomain __declspec-Schlüsselwort"
ms.assetid: 29d843cb-cb6b-4d1b-a48d-d928a877234d
caps.latest.revision: 23
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# appdomain
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass jede Anwendungsdomäne der verwalteten Anwendung eine eigene Kopie einer bestimmten globalen Variable oder statischen Membervariable haben soll.  Weitere Informationen finden Sie unter [Anwendungsdomänen und Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md).  
  
 Jede Anwendungsdomäne verfügt über eine eigene Kopie einer Anwendungsdomänenvariable.  Ein Konstruktor einer Anwendungsdomänenvariable wird ausgeführt, wenn eine Assembly in eine Anwendungsdomäne geladen wird, und der Destruktor wird ausgeführt, wenn die Anwendungsdomäne entladen wird.  
  
 Wenn alle Anwendungsdomänen innerhalb eines Prozesses in der Common Language Runtime eine globale Variable gemeinsam nutzen sollen, verwenden Sie den `__declspec(process)`\-Modifizierer.  `__declspec(process)` ist wirksam standardmäßig unter [\/clr](../build/reference/clr-common-language-runtime-compilation.md) wirksam und `__declspec(appdomain)` ist standardmäßig unter **\/clr:pure** wirksam.  `__declspec(appdomain)` wird unter **\/clr:safe** erzwungen.  
  
 `__declspec(appdomain)` ist nur gültig, wenn eine der **\/clr**\-Compileroptionen verwendet wird.  Nur eine globale Variable, eine statische Membervariable oder eine statische lokale Variable kann mit `__declspec(appdomain)` markiert werden.  Es ist nicht zulässig, `__declspec(appdomain)` auf statische Member von verwalteten Typen anzuwenden, da diese immer dieses Verhalten aufweisen.  
  
 Die Verwendung von `__declspec(appdomain)` ähnelt der Verwendung eines [lokalen Threadspeichers \(TLS\)](../parallel/thread-local-storage-tls.md).  Threads verfügen über einen eigenen Speicher, genau wie Anwendungsdomänen.  Die Verwendung `__declspec(appdomain)` stellt sicher, dass die globale Variable einen eigenen Speicher in jeder Anwendungsdomäne aufweist, die für die Anwendung erstellt wird.  
  
 Es gibt Einschränkungen beim Kombinieren der pro\-Prozess\- und pro\-AppDomain\-Variablen; Weitere Informationen finden Sie unter [Prozess](../cpp/process.md).  
  
 Beim Programmstart werden beispielsweise alle pro\-Prozess\-Variablen initialisiert, gefolgt von alle pro\-AppDomain\-Variablen.  Wenn eine pro\-Prozess\-Variable initialisiert wird, kann sie also nicht vom Wert einer pro\-AppDomain\-Variablen abhängen.  Es ist nicht üblich, die Verwendung \(Zuweisung\) der pro\-Prozess\- und pro\-AppDomain\-Variablen zu kombinieren.  
  
 Informationen darüber, wie eine Funktion in einer bestimmten Anwendungsdomäne aufgerufen werden, finden Sie unter [call\_in\_appdomain\-Funktion](../dotnet/call-in-appdomain-function.md).  
  
## Beispiel  
  
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
  
  **\_\_declspec\(process\) CGlobal::CGlobal\-Konstruktor**  
**\_\_declspec\(appdomain\) CGlobal::CGlobal\-Konstruktor**  
**Anfangswert**  
**process\_global value in appdomain 'declspec\_appdomain.exe': 10**  
**appdomain\_global value in appdomain 'declspec\_appdomain.exe': 10**  
**\_\_declspec\(appdomain\) CGlobal::CGlobal\-Konstruktor**  
**process\_global value in appdomain 'Domain 1': 10**  
**appdomain\_global value in appdomain 'Domain 1': 10**  
**\_\_declspec\(appdomain\) CGlobal::CGlobal\-Konstruktor**  
**process\_global value in appdomain 'Domain 2': 10**  
**appdomain\_global value in appdomain 'Domain 2': 10**  
**Geänderter Wert**  
**process\_global value in appdomain 'declspec\_appdomain.exe': 20**  
**appdomain\_global value in appdomain 'declspec\_appdomain.exe': 10**  
**process\_global value in appdomain 'Domain 1': 20**  
**appdomain\_global value in appdomain 'Domain 1': 11**  
**process\_global value in appdomain 'Domain 2': 20**  
**appdomain\_global value in appdomain 'Domain 2': 12**  
**\_\_declspec\(appdomain\) CGlobal::~CGlobal\-Destruktor**  
**\_\_declspec\(appdomain\) CGlobal::~CGlobal\-Destruktor**  
**\_\_declspec\(appdomain\) CGlobal::~CGlobal\-Destruktor**  
**\_\_declspec\(process\) CGlobal::~CGlobal\-Destruktor**   
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)