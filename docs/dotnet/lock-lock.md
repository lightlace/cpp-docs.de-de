---
title: Lock::lock | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- lock::lock
- lock.lock
- msclr.lock.lock
- msclr::lock::lock
dev_langs:
- C++
helpviewer_keywords:
- lock constructor
ms.assetid: c9ad6c71-36ec-49c5-8ebd-f5c3a0cc94f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 76991eb9910e046ecdb76f3f169f7d410b38288e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428734"
---
# <a name="locklock"></a>lock::lock

Erstellt eine `lock` Objekt, das optional wartet unbegrenzt, Abrufen von der Sperre für eine bestimmte Zeit oder überhaupt nicht.

## <a name="syntax"></a>Syntax

```
template<class T> lock(
   T ^ _object
);
template<class T> lock(
   T ^ _object,
   int _timeout
);
template<class T> lock(
   T ^ _object,
   System::TimeSpan _timeout
);
template<class T> lock(
   T ^ _object,
   lock_later
);
```

#### <a name="parameters"></a>Parameter

*_Object*<br/>
Das Objekt, das gesperrt werden.

*_Timeout*<br/>
Timeoutwert in Millisekunden oder als eine <xref:System.TimeSpan>.

## <a name="exceptions"></a>Ausnahmen

Löst <xref:System.ApplicationException> Wenn Sperrenübernahme nicht vor dem Timeout auftritt.

## <a name="remarks"></a>Hinweise

Die ersten drei Formulare des Konstruktors, auf eine Sperre einzurichten versucht `_object` innerhalb des angegebenen Zeitlimits (oder <xref:System.Threading.Timeout.Infinite> Wenn keine Angabe erfolgt).

Ruft die vierte Form des Konstruktors eine Sperre nicht auf `_object`. `lock_later` ist ein Mitglied der [Lock_when-Enumeration](../dotnet/lock-when-enum.md). Verwendung [lock::acquire](../dotnet/lock-acquire.md) oder [lock::try_acquire](../dotnet/lock-try-acquire.md) , der in diesem Fall eine Sperre.

Die Sperre wird automatisch freigegeben werden, wenn der Destruktor aufgerufen wird.

`_object` darf nicht <xref:System.Threading.ReaderWriterLock> sein.  Wenn es sich handelt, führt ein Compilerfehler ausgegeben.

## <a name="example"></a>Beispiel

Dieses Beispiel verwendet eine einzelne Instanz einer Klasse auf mehrere Threads.  Die Klasse verwendet eine Sperre auf sich selbst, um sicherzustellen, dass der Zugriff auf seine internen Daten für jeden Thread konsistent sind.  Thread der hauptanwendung verwendet eine Sperre für dieselbe Instanz der Klasse verwendet, um in regelmäßigen Abständen überprüfen, um festzustellen, ob alle Worker-Threads noch vorhanden sind, und wartet, bis alle Worker-Threads zu beenden, ihre Aufgaben abgeschlossen haben.

```
// msl_lock_lock.cpp
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
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
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

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\lock.h >

**Namespace** Msclr

## <a name="see-also"></a>Siehe auch

[lock-Members](../dotnet/lock-members.md)<br/>
[lock::~lock](../dotnet/lock-tilde-lock.md)<br/>
[lock::acquire](../dotnet/lock-acquire.md)<br/>
[lock::try_acquire](../dotnet/lock-try-acquire.md)