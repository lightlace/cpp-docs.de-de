---
title: Intrinsische Funktionen „_InterlockedCompareExchange“
ms.date: 11/04/2016
f1_keywords:
- _InterlockedCompareExchange_HLERelease
- _InterlockedCompareExchange8_nf
- _InterlockedCompareExchange16_acq_cpp
- _InterlockedCompareExchange_acq_cpp
- _InterlockedCompareExchange16_rel_cpp
- _InterlockedCompareExchange64_rel_cpp
- _InterlockedCompareExchange_cpp
- _InterlockedCompareExchange16_cpp
- _InterlockedCompareExchange64_acq_cpp
- _InterlockedCompareExchange_acq
- _InterlockedCompareExchange64_rel
- _InterlockedCompareExchange64_nf
- _InterlockedCompareExchange_rel_cpp
- _InterlockedCompareExchange16_nf
- _InterlockedCompareExchange8
- _InterlockedCompareExchange64_np
- _InterlockedCompareExchange16_rel
- _InterlockedCompareExchange64_acq
- _InterlockedCompareExchange8_rel
- _InterlockedCompareExchange_HLEAcquire
- _InterlockedCompareExchange64_HLERelease
- _InterlockedCompareExchange64_cpp
- _InterlockedCompareExchange_np
- _InterlockedCompareExchange8_acq
- _InterlockedCompareExchange16_acq
- _InterlockedCompareExchange_rel
- _InterlockedCompareExchange64_HLEAcquire
- _InterlockedCompareExchange64
- _InterlockedCompareExchange16
- _InterlockedCompareExchange
helpviewer_keywords:
- _InterlockedCompareExchange16 intrinsic
- _InterlockedCompareExchange_acq intrinsic
- InterlockedCompareExchange_acq intrinsic
- _InterlockedCompareExchange intrinsic
- InterlockedCompareExchange64 intrinsic
- _InterlockedCompareExchange64_acq intrinsic
- InterlockedCompareExchange16 intrinsic
- _InterlockedCompareExchange_rel intrinsic
- InterlockedCompareExchange intrinsic
- InterlockedCompareExchange64_acq intrinsic
- InterlockedCompareExchange_rel intrinsic
- _InterlockedCompareExchange64 intrinsic
- InterlockedCompareExchange64_rel intrinsic
- _InterlockedCompareExchange64_rel intrinsic
ms.assetid: c3ad79c0-a523-4930-a3a4-69a65d7d5c81
ms.openlocfilehash: 2a583c953c98df49b45eecd2040905b253567cfe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577233"
---
# <a name="interlockedcompareexchange-intrinsic-functions"></a>Intrinsische Funktionen „_InterlockedCompareExchange“

**Microsoft-spezifisch**

Führt einen ineinandergreifenden Vergleich und Austausch durch.

## <a name="syntax"></a>Syntax

```
long _InterlockedCompareExchange(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
long _InterlockedCompareExchange_acq(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
long _InterlockedCompareExchange_HLEAcquire(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
long _InterlockedCompareExchange_HLERelease(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
long _InterlockedCompareExchange_np(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
long _InterlockedCompareExchange_rel(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
char _InterlockedCompareExchange8(
   char volatile * Destination,
   char Exchange,
   char Comparand
);
char _InterlockedCompareExchange8_acq(
   char volatile * Destination,
   char Exchange,
   char Comparand
);
char _InterlockedCompareExchange8_nf(
   char volatile * Destination,
   char Exchange,
   char Comparand
);
char _InterlockedCompareExchange8_rel(
   char volatile * Destination,
   char Exchange,
   char Comparand
);
short _InterlockedCompareExchange16(
   short volatile * Destination,
   short Exchange,
   short Comparand
);
short _InterlockedCompareExchange16_acq(
   short volatile * Destination,
   short Exchange,
   short Comparand
);
short _InterlockedCompareExchange16_nf(
   short volatile * Destination,
   short Exchange,
   short Comparand
);
short _InterlockedCompareExchange16_np(
   short volatile * Destination,
   short Exchange,
   short Comparand
);
short _InterlockedCompareExchange16_rel(
   short volatile * Destination,
   short Exchange,
   short Comparand
);
__int64 _InterlockedCompareExchange64(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_acq(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_HLEAcquire (
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_HLERelease(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_nf(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_np(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_rel(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
```

#### <a name="parameters"></a>Parameter

*Ziel*<br/>
[in, out] Zeiger auf den Zielwert. Die Zeichen wird ignoriert.

*Exchange*<br/>
[in] Exchange-Wert. Die Zeichen wird ignoriert.

*Comparand-Parameter*<br/>
[in] Wert, der Vergleich mit dem Ziel. Die Zeichen wird ignoriert.

## <a name="return-value"></a>Rückgabewert

Der Rückgabewert ist der Anfangswert des `Destination`-Zeigers.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|Header|
|---------------|------------------|------------|
|`_InterlockedCompareExchange`, `_InterlockedCompareExchange8`, `_InterlockedCompareExchange16`, `_InterlockedCompareExchange64`|X86, ARM, x64|\<intrin.h>|
|`_InterlockedCompareExchange_acq`, `_InterlockedCompareExchange_rel`, `_InterlockedCompareExchange8_acq`, `_InterlockedCompareExchange8_nf`, `_InterlockedCompareExchange8_rel`,`_InterlockedCompareExchange16_acq`, `_InterlockedCompareExchange16_nf`, `_InterlockedCompareExchange16_rel`, `_InterlockedCompareExchange64_acq`, `_InterlockedCompareExchange64_nf`, `_InterlockedCompareExchange64_rel`,|ARM|\<intrin.h>|
|`_InterlockedCompareExchange_np`, `_InterlockedCompareExchange16_np`, `_InterlockedCompareExchange64_np`|x64|\<intrin.h>|
|`_InterlockedCompareExchange_HLEAcquire`, `_InterlockedCompareExchange_HLERelease`, `_InterlockedCompareExchange64_HLEAcquire`, `_InterlockedCompareExchange64_HLERelease`|x86, x64|\<immintrin.h>|

## <a name="remarks"></a>Hinweise

`_InterlockedCompareExchange` führt einen atomaren Vergleich des `Destination`-Werts mit dem `Comparand`-Wert durch. Wenn der `Destination`-Wert gleich dem `Comparand`-Wert ist, wird der `Exchange`-Wert in der von `Destination` angegebenen Adresse gespeichert. Andernfalls wird kein Vorgang ausgeführt.

`_InterlockedCompareExchange` bietet systeminterne compilerunterstützung für die Win32-Windows-SDK [InterlockedCompareExchange](/windows/desktop/api/winbase/nf-winbase-interlockedcompareexchange) Funktion.

Es gibt mehrere Varianten von `_InterlockedCompareExchange`, die sich basierend auf den beinhalteten Datentypen und in Abhängigkeit davon unterscheiden, ob prozessorspezifische Semantiken zum Abrufen bzw. Freigeben verwendet werden.

Die `_InterlockedCompareExchange`-Funktion funktioniert mit langen ganzen Zahlen, `_InterlockedCompareExchange8` funktioniert mit ganzzahligen 8-Bit-Werten, `_InterlockedCompareExchange16` funktioniert mit kurzen ganzen Zahlen, und `_InterlockedCompareExchange64` funktioniert mit ganzzahligen 64-Bit-Werten.

Verwenden Sie auf ARM-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel` für Semantiken zum Abrufen bzw. Freigeben, z. B. am Beginn und am Ende eines kritischen Abschnitts. Die systeminternen ARM-Funktionen mit dem Suffix `_nf` („no fence“) dienen nicht als Arbeitsspeicherbarriere.

Die systeminternen Funktionen mit dem Suffix `_np` („no prefetch“) verhindern, dass ein möglicher Vorabrufvorgang vom Compiler eingefügt wird.

Auf Intel-Plattformen, die Hardware Lock Elision (HLE)-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis für den Prozessor, wie die Leistung durch den Wegfall der Schreibsperre in der Hardware beschleunigt werden kann. Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.

Diese Routinen sind nur als systeminterne Funktionen verfügbar.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird `_InterlockedCompareExchange` für die einfache Low-Level-Threadsynchronisierung verwendet. Der Ansatz unterliegt gewissen Einschränkungen als Grundlage für die Multithreadprogrammierung. Er wird zur Veranschaulichung der typischen Verwendung von ineinandergreifenden systeminternen Funktionen dargestellt. Verwenden Sie für optimale Ergebnisse die Windows-API. Weitere Informationen zur Multithreadprogrammierung finden Sie [Schreiben von Win32-Multithreadprogrammen](../parallel/writing-a-multithreaded-win32-program.md).

```
// intrinExample.cpp
// compile with: /EHsc /O2
// Simple example of using _Interlocked* intrinsics to
// do manual synchronization
//
// Add [-DSKIP_LOCKING] to the command line to disable
// the locking. This will cause the threads to execute out
// of sequence.

#define _CRT_RAND_S

#include "windows.h"

#include <iostream>
#include <queue>
#include <intrin.h>

using namespace std;

// --------------------------------------------------------------------

// if defined, will not do any locking on shared data
//#define SKIP_LOCKING

// A common way of locking using _InterlockedCompareExchange.
// Please refer to other sources for a discussion of the many issues
// involved. For example, this particular locking scheme performs well
// when lock contention is low, as the while loop overhead is small and
// locks are acquired very quickly, but degrades as many callers want
// the lock and most threads are doing a lot of interlocked spinning.
// There are also no guarantees that a caller will ever acquire the
// lock.
namespace MyInterlockedIntrinsicLock
{
    typedef unsigned LOCK, *PLOCK;

#pragma intrinsic(_InterlockedCompareExchange, _InterlockedExchange)

    enum {LOCK_IS_FREE = 0, LOCK_IS_TAKEN = 1};

    void Lock(PLOCK pl)
    {
#if !defined(SKIP_LOCKING)
        // If *pl == LOCK_IS_FREE, it is set to LOCK_IS_TAKEN
        // atomically, so only 1 caller gets the lock.
        // If *pl == LOCK_IS_TAKEN,
        // the result is LOCK_IS_TAKEN, and the while loop keeps spinning.
        while (_InterlockedCompareExchange((long *)pl,
                                           LOCK_IS_TAKEN, // exchange
                                           LOCK_IS_FREE)  // comparand
               == LOCK_IS_TAKEN)
        {
            // spin!
        }
        // This will also work.
        //while (_InterlockedExchange(pl, LOCK_IS_TAKEN) ==
        //                             LOCK_IS_TAKEN)
        //{
        //    // spin!
        //}

        // At this point, the lock is acquired.
#endif
    }

    void Unlock(PLOCK pl) {
#if !defined(SKIP_LOCKING)
        _InterlockedExchange((long *)pl, LOCK_IS_FREE);
#endif
    }
}

// ------------------------------------------------------------------

// Data shared by threads

queue<int> SharedQueue;
MyInterlockedIntrinsicLock::LOCK SharedLock;
int TicketNumber;

// ------------------------------------------------------------------

DWORD WINAPI
ProducerThread(
    LPVOID unused
    )
{
    unsigned int randValue;
    while (1) {
        // Acquire shared data. Enter critical section.
        MyInterlockedIntrinsicLock::Lock(&SharedLock);

        //cout << ">" << TicketNumber << endl;
        SharedQueue.push(TicketNumber++);

        // Release shared data. Leave critical section.
        MyInterlockedIntrinsicLock::Unlock(&SharedLock);

        rand_s(&randValue);
        Sleep(randValue % 20);
    }

    return 0;
}

DWORD WINAPI
ConsumerThread(
    LPVOID unused
    )
{
    while (1) {
        // Acquire shared data. Enter critical section
        MyInterlockedIntrinsicLock::Lock(&SharedLock);

        if (!SharedQueue.empty()) {
            int x = SharedQueue.front();
            cout << "<" << x << endl;
            SharedQueue.pop();
        }

        // Release shared data. Leave critical section
        MyInterlockedIntrinsicLock::Unlock(&SharedLock);

        unsigned int randValue;
        rand_s(&randValue);
        Sleep(randValue % 20);
    }
    return 0;
}

int main(
    void
    )
{
    const int timeoutTime = 500;
    int unused1, unused2;
    HANDLE threads[4];

    // The program creates 4 threads:
    // two producer threads adding to the queue
    // and two consumers taking data out and printing it.
    threads[0] = CreateThread(NULL,
                              0,
                              ProducerThread,
                              &unused1,
                              0,
                              (LPDWORD)&unused2);

    threads[1] = CreateThread(NULL,
                              0,
                              ConsumerThread,
                              &unused1,
                              0,
                              (LPDWORD)&unused2);

    threads[2] = CreateThread(NULL,
                              0,
                              ProducerThread,
                              &unused1,
                              0,
                              (LPDWORD)&unused2);

    threads[3] = CreateThread(NULL,
                              0,
                              ConsumerThread,
                              &unused1,
                              0,
                              (LPDWORD)&unused2);

    WaitForMultipleObjects(4, threads, TRUE, timeoutTime);

    return 0;
}
```

```Output
<0
<1
<2
<3
<4
<5
<6
<7
<8
<9
<10
<11
<12
<13
<14
<15
<16
<17
<18
<19
<20
<21
<22
<23
<24
<25
<26
<27
<28
<29
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_InterlockedCompareExchange128](../intrinsics/interlockedcompareexchange128.md)<br/>
[Intrinsische Funktionen „_InterlockedCompareExchangePointer“](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Konflikt mit dem x86-Compiler](../build/conflicts-with-the-x86-compiler.md)