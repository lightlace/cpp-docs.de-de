---
title: "lock::is_locked"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "is_locked"
  - "msclr::lock::is_locked"
  - "lock::is_locked"
  - "msclr::lock.is_locked"
  - "lock.is_locked"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock::is_locked"
ms.assetid: d888827c-8052-47c6-87a2-8c42f60a688d
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# lock::is_locked
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob eine Sperre befindet.  
  
## Syntax  
  
```  
bool is_locked();  
```  
  
## Rückgabewert  
 `true`, wenn eine Sperre vorhanden ist; andernfalls `false`.  
  
## Beispiel  
 In diesem Beispiel wird eine einzelne Instanz einer Klasse über mehrere Threads.  Die Klasse verwendet eine Sperre auf sich, um sicherzustellen, dass auf auf die internen Daten für jeden Thread konsistent sind.  Der Hauptthread verwendet eine Sperre auf der gleichen Instanz der Klasse, die in regelmäßigen Abständen zu überprüfen, dass Arbeitsthreads ggf. anzuzeigen noch vorhanden, und wartet, bis alle Arbeitsthreads beendet haben ihre Aufgaben abgeschlossen.  
  
```  
// msl_lock_is_locked.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
ref class CounterClass {  
private:  
   int Counter;     
  
public:  
   property int ThreadCount;  
  
   // function called by multiple threads, use lock to keep Counter consistent  
   // for each thread  
   void UseCounter() {  
      try {  
         lock l(this); // wait infinitely  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         for (int i = 0; i < 10; i++) {  
            Counter++;  
            Thread::Sleep(10);  
         }  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         Counter = 0;  
         // lock is automatically released when it goes out of scope and its destructor is called  
      }  
      catch (...) {  
         Console::WriteLine("Couldn't acquire lock!");  
      }  
  
      ThreadCount--;  
   }  
};  
  
int main() {  
   // create a few threads to contend for access to the shared data  
   CounterClass^ cc = gcnew CounterClass;  
   array<Thread^>^ tarr = gcnew array<Thread^>(5);  
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);  
   for (int i = 0; i < tarr->Length; i++) {  
      tarr[i] = gcnew Thread(startDelegate);  
      cc->ThreadCount++;  
      tarr[i]->Start();  
   }  
  
   // keep our main thread alive until all worker threads have completed  
   lock l(cc, lock_later); // don't lock now, just create the object  
   while (true) {  
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't  
      if (l.is_locked()) { // check if we got the lock  
         if (0 == cc->ThreadCount) {  
            Console::WriteLine("All threads completed.");  
            break; // all threads are gone, exit while  
         }  
         else {  
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);  
            l.release(); // some threads exist, let them do their work  
         }  
      }  
   }  
}  
```  
  
  **Im Thread 3, Zähler \= 0**  
**Im Thread 3, Zähler \= 10**  
**Im Thread 5, Zähler \= 0**  
**Im Thread 5, Zähler \= 10**  
**Im Thread 4, Zähler \= 0**  
**Im Thread 4, Zähler \= 10**  
**Im Thread 7, Zähler \= 0**  
**Im Thread 7, Zähler \= 10**  
**Im Thread 6, Zähler \= 0**  
**Im Thread 6, Zähler \= 10**  
**Alle Threads abgeschlossen.**   
## Anforderungen  
 **Headerdatei** \<msclr\\lock.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [lock\-Member](../dotnet/lock-members.md)   
 [lock::operator bool](../dotnet/lock-operator-bool.md)