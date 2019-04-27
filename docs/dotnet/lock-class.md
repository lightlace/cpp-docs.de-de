---
title: lock-Klasse
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::lock::lock
- msclr::lock::is_locked
- msclr::lock.is_locked
- msclr::lock::acquire
- msclr::lock::try_acquire
- msclr::lock::release
- msclr::lock::operator==
- msclr::lock::operator!=
helpviewer_keywords:
- msclr::lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: 43418da36aa2d87608a9d672e4345d24011be0b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153438"
---
# <a name="lock-class"></a>lock-Klasse

Diese Klasse automatisiert die Verwendung einer Sperre für den Zugriff auf ein Objekt von mehreren Threads zu synchronisieren.  Bei der Erstellung Ruft die Sperre, und wenn es sich um Versionen zerstört die Sperre.

## <a name="syntax"></a>Syntax

```cpp
ref class lock;
```

## <a name="remarks"></a>Hinweise

`lock` ist nur für CLR-Objekte verfügbar und kann nur in CLR-Code verwendet werden.

Intern wird die Lock-Klasse verwendet <xref:System.Threading.Monitor> zum Synchronisieren des Zugriffs. Weitere Informationen finden Sie unter den angegebenen Artikel.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|---------|-----------|
|[lock::lock](#lock)|Erstellt eine `lock` Objekt, das optional wartet unbegrenzt, Abrufen von der Sperre für eine bestimmte Zeit oder überhaupt nicht.|
|[lock::~lock](#tilde-lock)|Destructs eine `lock` Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|---------|-----------|
|[lock::acquire](#acquire)|Richtet eine Sperre für ein Objekt, das optional wartet unbegrenzt, Abrufen von der Sperre für eine bestimmte Zeit oder überhaupt nicht.|
|[lock::is_locked](#is-locked)|Gibt an, ob eine Sperre gehalten wird.|
|[lock::release](#release)|Gibt eine Sperre frei.|
|[lock::try_acquire](#try-acquire)|Ruft eine Sperre für ein Objekt, das Warten auf eines angegebenen Zeitraum und die Rückgabe einer `bool` um den Erfolg des Abrufs statt einer Ausnahme zu melden.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|---------|-----------|
|[lock::operator&nbsp;bool](#operator-bool)|Operator für die Verwendung von `lock` in einem bedingten Ausdruck.|
|[lock::operator==](#operator-equality)|Equality-Operator.|
|[lock::operator!=](#operator-inequality)|Ungleichheitsoperator.|

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\lock.h >

**Namespace** Msclr



## <a name="lock"></a>lock::lock

Erstellt eine `lock` Objekt, das optional wartet unbegrenzt, Abrufen von der Sperre für eine bestimmte Zeit oder überhaupt nicht.

```cpp
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

### <a name="parameters"></a>Parameter

*_object*<br/>
Das Objekt, das gesperrt werden.

*_timeout*<br/>
Der Timeoutwert in Millisekunden oder als eine <xref:System.TimeSpan>.

### <a name="exceptions"></a>Ausnahmen

Löst <xref:System.ApplicationException> Sperrenübernahme tritt vor dem Timeout auf.

### <a name="remarks"></a>Hinweise

Die ersten drei Formulare des Konstruktors versuchen, eine Sperre abzurufen, auf `_object` innerhalb des angegebenen Zeitlimits (oder <xref:System.Threading.Timeout.Infinite> Wenn keine Angabe erfolgt).

Die vierte Form des Konstruktors nicht Ruft eine Sperre auf `_object`. `lock_later` ist ein Mitglied der [Lock_when-Enumeration](../dotnet/lock-when-enum.md). Verwendung [lock::acquire](../dotnet/lock-acquire.md) oder [lock::try_acquire](../dotnet/lock-try-acquire.md) , der in diesem Fall eine Sperre.

Die Sperre wird automatisch freigegeben werden, wenn der Destruktor aufgerufen wird.

`_object` nicht möglich, <xref:System.Threading.ReaderWriterLock>.  Wenn es sich handelt, führt ein Compilerfehler ausgegeben.

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet eine einzelne Instanz einer Klasse über mehrere Threads. Die Klasse verwendet eine Sperre auf sich selbst, um sicherzustellen, dass der Zugriff auf seine internen Daten für jeden Thread konsistent sind. Thread der hauptanwendung verwendet eine Sperre für dieselbe Instanz der Klasse verwendet, um in regelmäßigen Abständen überprüfen, wenn alle Arbeitsthreads noch vorhanden sind. Klicken Sie dann die hauptanwendung wartet zu beenden, bis alle Arbeitsthreads ihre Aufgaben abgeschlossen haben.

```cpp
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

## <a name="tilde-lock"></a>lock::~lock

Destructs eine `lock` Objekt.

```cpp
~lock();
```

### <a name="remarks"></a>Hinweise

Der Destruktor ruft [lock::release](../dotnet/lock-release.md).

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet eine einzelne Instanz einer Klasse über mehrere Threads.  Die Klasse verwendet eine Sperre auf sich selbst, um sicherzustellen, dass der Zugriff auf seine internen Daten für jeden Thread konsistent sind.  Thread der hauptanwendung verwendet eine Sperre für dieselbe Instanz der Klasse verwendet, um in regelmäßigen Abständen überprüfen, wenn alle Arbeitsthreads noch vorhanden sind. Klicken Sie dann die hauptanwendung wartet zu beenden, bis alle Arbeitsthreads ihre Aufgaben abgeschlossen haben.

```cpp
// msl_lock_dtor.cpp
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

## <a name="acquire"></a>lock::acquire

Richtet eine Sperre für ein Objekt, das optional wartet unbegrenzt, Abrufen von der Sperre für eine bestimmte Zeit oder überhaupt nicht.

```cpp
void acquire();
void acquire(
   int _timeout
);
void acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>Parameter

*_timeout*<br/>
Timeoutwert in Millisekunden oder als eine <xref:System.TimeSpan>.

### <a name="exceptions"></a>Ausnahmen

Löst <xref:System.ApplicationException> Sperrenübernahme tritt vor dem Timeout auf.

### <a name="remarks"></a>Hinweise

Wenn kein Timeoutwert angegeben wird, wird das standardmäßige Timeout <xref:System.Threading.Timeout.Infinite>.

Wenn eine Sperre bereits abgerufen wurde, hat diese Funktion mit "nothing".

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet eine einzelne Instanz einer Klasse über mehrere Threads.  Die Klasse verwendet eine Sperre auf sich selbst, um sicherzustellen, dass der Zugriff auf seine internen Daten für jeden Thread konsistent sind. Thread der hauptanwendung verwendet eine Sperre für dieselbe Instanz der Klasse verwendet, um in regelmäßigen Abständen überprüfen, wenn alle Arbeitsthreads noch vorhanden sind. Klicken Sie dann die hauptanwendung wartet zu beenden, bis alle Arbeitsthreads ihre Aufgaben abgeschlossen haben.

```cpp
// msl_lock_acquire.cpp
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

## <a name="is-locked"></a>lock::is_locked

Gibt an, ob eine Sperre gehalten wird.

```cpp
bool is_locked();
```

### <a name="return-value"></a>Rückgabewert

`true` Wenn eine Sperre aufrechterhalten wird, `false` andernfalls.

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet eine einzelne Instanz einer Klasse über mehrere Threads.  Die Klasse verwendet eine Sperre auf sich selbst, um sicherzustellen, dass der Zugriff auf seine internen Daten für jeden Thread konsistent sind.  Thread der hauptanwendung verwendet eine Sperre für dieselbe Instanz der Klasse verwendet, um in regelmäßigen Abständen überprüfen, um festzustellen, ob alle Worker-Threads noch vorhanden sind, und wartet, bis alle Worker-Threads zu beenden, ihre Aufgaben abgeschlossen haben.

```cpp
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

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="operator-bool"></a>Lock::Operator "bool"

Operator für die Verwendung von `lock` in einem bedingten Ausdruck.

```cpp
operator bool();
```

### <a name="return-value"></a>Rückgabewert

`true` Wenn eine Sperre aufrechterhalten wird, `false` andernfalls.

### <a name="remarks"></a>Hinweise

Dieser Operator konvertiert tatsächlich in `_detail_class::_safe_bool` ist sicherer als `bool` , da es in einen ganzzahligen Typ konvertiert werden kann.

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet eine einzelne Instanz einer Klasse über mehrere Threads.  Die Klasse verwendet eine Sperre auf sich selbst, um sicherzustellen, dass der Zugriff auf seine internen Daten für jeden Thread konsistent sind. Thread der hauptanwendung verwendet eine Sperre für dieselbe Instanz der Klasse verwendet, um in regelmäßigen Abständen überprüfen, wenn alle Arbeitsthreads noch vorhanden sind. Die hauptanwendung wartet zu beenden, bis alle Arbeitsthreads ihre Aufgaben abgeschlossen haben.

```cpp
// msl_lock_op_bool.cpp
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
      if (l) { // use bool operator to check for lock
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

## <a name="release"></a>lock::release

Gibt eine Sperre frei.

```cpp
void release();
```

### <a name="remarks"></a>Hinweise

Wenn keine Sperre gehalten wird, `release` hat keine Auswirkungen.

Sie müssen nicht explizit aufrufen dieser Funktion. Wenn eine `lock` Objekt wird außerhalb des gültigen Bereichs, dessen Destruktor ruft `release`.

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet eine einzelne Instanz einer Klasse über mehrere Threads. Die Klasse verwendet eine Sperre auf sich selbst, um sicherzustellen, dass der Zugriff auf seine internen Daten für jeden Thread konsistent sind. Thread der hauptanwendung verwendet eine Sperre für dieselbe Instanz der Klasse verwendet, um in regelmäßigen Abständen überprüfen, wenn alle Arbeitsthreads noch vorhanden sind. Klicken Sie dann die hauptanwendung wartet zu beenden, bis alle Arbeitsthreads ihre Aufgaben abgeschlossen haben.

```cpp
// msl_lock_release.cpp
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

## <a name="try-acquire"></a>lock::try_acquire

Ruft eine Sperre für ein Objekt, das Warten auf eines angegebenen Zeitraum und die Rückgabe einer `bool` um den Erfolg des Abrufs statt einer Ausnahme zu melden.

```cpp
bool try_acquire(
   int _timeout_ms
);
bool try_acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>Parameter

*_timeout*<br/>
Timeoutwert in Millisekunden oder als eine <xref:System.TimeSpan>.

### <a name="return-value"></a>Rückgabewert

`true` Wenn die Sperre abgerufen wurde, `false` andernfalls.

### <a name="remarks"></a>Hinweise

Wenn eine Sperre bereits abgerufen wurde, hat diese Funktion mit "nothing".

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet eine einzelne Instanz einer Klasse über mehrere Threads. Die Klasse verwendet eine Sperre auf sich selbst, um sicherzustellen, dass der Zugriff auf seine internen Daten für jeden Thread konsistent sind. Thread der hauptanwendung verwendet eine Sperre für dieselbe Instanz der Klasse verwendet, um in regelmäßigen Abständen überprüfen, wenn alle Arbeitsthreads noch vorhanden sind. Klicken Sie dann die hauptanwendung wartet zu beenden, bis alle Arbeitsthreads ihre Aufgaben abgeschlossen haben.

```cpp
// msl_lock_try_acquire.cpp
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

## <a name="operator-equality"></a>lock::operator==

Equality-Operator.

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>Parameter

*t*<br/>
Das Objekt auf Gleichheit verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt `true` Wenn `t` entspricht das Sperrobjekt und `false` andernfalls.

### <a name="example"></a>Beispiel

```cpp
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="operator-inequality"></a>Lock::Operator! =

Ungleichheitsoperator.

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>Parameter

*t*<br/>
Das Objekt zu vergleichende Instanz.

### <a name="return-value"></a>Rückgabewert

Gibt `true` Wenn `t` unterscheidet sich von der Sperrobjekt und `false` andernfalls.

### <a name="example"></a>Beispiel

```cpp
// msl_lock_op_ineq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   Object^ o2 = gcnew Object;
   lock l1(o1);
   if (l1 != o2) {
      Console::WriteLine("Inequal!");
   }
}
```

```Output
Inequal!
```