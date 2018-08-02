---
title: Thread | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- thread_cpp
dev_langs:
- C++
helpviewer_keywords:
- thread local storage (TLS)
- thread __declspec keyword
- TLS (thread local storage), compiler implementation
- __declspec keyword [C++], thread
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 148e42a79ef7c20b7b35c3ec570212574782c1f6
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462091"
---
# <a name="thread"></a>Thread

**Microsoft-spezifisch**

Die **Thread** erweiterte Speicherklassenmodifizierer wird verwendet, um eine threadlokale Variable zu deklarieren. Verwenden Sie für das Portable entspricht in C ++ 11 und höher, die [Thread_local](../cpp/storage-classes-cpp.md#thread_local) Speicherklassenspezifizierer für portablen Code. Auf Windows `thread_local` wird implementiert, mit **__declspec(thread)**.

## <a name="syntax"></a>Syntax

> **__declspec (Thread)** *Deklarator*  

## <a name="remarks"></a>Hinweise

Threadlokaler Speicher (TLS) ist der Mechanismus, mit dem jeder Thread in einem Multithreadprozess den Speicher für threadspezifische Daten zuordnet. In den standardmäßigen Multithreadprogrammen werden Daten auf allen Threads eines angegebenen Prozesses freigegeben, während der threadlokale Speicher der Mechanismus zum Zuordnen der threadspezifischen Daten ist. Eine vollständige Erörterung der Threads, finden Sie unter [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Deklarationen von threadlokalen Variablen müssen verwenden [erweiterte Attributsyntax](../cpp/declspec.md) und die **__declspec** Schlüsselwort mit dem **Thread** Schlüsselwort. Mit folgendem Code wird z. B. eine Ganzzahl-TLS-Variable deklariert und mit einem Wert initialisiert:

```cpp
__declspec( thread ) int tls_i = 1;
```

Wenn Sie Thread-lokalen Variablen in dynamisch geladen Bibliotheken verwenden zu können, müssen Sie Faktoren bewusst sein, die dazu führen können, dass eine Thread-Local-Variable, die nicht ordnungsgemäß initialisiert werden:

1. Wenn die Variable mit einem Funktionsaufruf (einschließlich Konstruktoren) initialisiert wird, wird diese Funktion nur aufgerufen werden, für den Thread, der Binary/laden die DLL in den Prozess verursacht hat, und klicken Sie nach diesen Threads, die gestartet wird, nach dem die Binary/DLL geladen wurde. Die Initialisierungsfunktionen werden nicht für jeden Thread aufgerufen, die bereits ausgeführt wurde, wenn die DLL geladen wurde. Dynamische Initialisierung tritt auf, auf den DllMain-Aufruf für DLL_THREAD_ATTACH, aber die DLL nie Ruft die Nachricht, wenn die DLL im Prozess nicht, wenn der Thread gestartet wird.

1. Thread-lokalen Variablen, die statisch mit konstanten Werten initialisiert werden, sind für alle Threads in der Regel ordnungsgemäß initialisiert. Ab Dezember 2017 ist gibt es eine bekannte Konformitätsproblem in der Microsoft Visual C++-Compiler, bei dem erhalten der Constexpr-Variablen, dynamisch statt statische Initialisierung.

   Hinweis: Beide Probleme werden voraussichtlich in zukünftigen Updates des Compilers behoben werden.

Darüber hinaus müssen Sie diese Richtlinien beachten, wenn Sie threadlokale Objekte und Variablen zu deklarieren:

- Sie können anwenden, die **Thread** -Attribut nur auf Datendeklarationen und Klassen und Definitionen. **Thread** kann nicht für Funktionsdeklarationen oder-Definitionen verwendet werden.

- Sie können angeben, die **Thread** Attribut nur für Datenelemente mit statischer Speicherdauer. Hierzu zählen globale Datenobjekte (sowohl **statische** und **"extern"**), lokale statische Objekte sowie statische Datenmember von Klassen. Sie können automatische Datenobjekte mit nicht deklarieren die **Thread** Attribut.

- Verwenden Sie die **Thread** Attribut für die Deklaration und die Definition eines threadlokalen Objekts, ob die Deklaration und Definition in der gleichen Datei oder in separaten Dateien auftreten.

- Sie können keine der **Thread** Attribut als Typmodifizierer.

- Da die Deklaration von Objekten, verwenden die **Thread** Attribut zulässig ist, diese beiden Beispiele semantisch gleichwertig:

    ```cpp
    // declspec_thread_2.cpp
    // compile with: /LD
    __declspec( thread ) class B {
    public:
       int data;
    } BObject;   // BObject declared thread local.

    class B2 {
    public:
       int data;
    };
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.
    ```

- In Standard-C ist die Initialisierung eines Objekts oder einer Variablen mit einem Ausdruck zulässig, der einen Verweis auf sich selbst enthält. Dies gilt jedoch nur für Objekte, die keinen statischen Wertebereich aufweisen. Obwohl in C++ diese dynamische Objektinitialisierung mit einem Ausdruck, der einen Verweis auf sich selbst enthält, normalerweise zulässig ist, ist dieser Initialisierungstyp für threadlokale Objekte nicht zulässig. Zum Beispiel:

   ```cpp
   // declspec_thread_3.cpp
   // compile with: /LD
   #define Thread __declspec( thread )
   int j = j;   // Okay in C++; C error
   Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
   ```

   Beachten Sie, dass eine **"sizeof"** Ausdruck, der das initialisierte Objekt enthält einen Verweis auf sich selbst stellt keine dar und ist in C und C++ zulässig.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch
 [__declspec](../cpp/declspec.md)  
 [Schlüsselwörter](../cpp/keywords-cpp.md)  
 [Threadlokaler Speicher (TLS)](../parallel/thread-local-storage-tls.md)  