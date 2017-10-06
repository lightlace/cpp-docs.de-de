---
title: Thread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: f460497071445cff87308fa9bf6e0d43c6f13a3e
ms.openlocfilehash: 7261dc1d6d76eeac8a6b2959bc9bb6fc3c98a66e
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="thread"></a>Thread

**Microsoft-spezifisch**  
Die **Thread** erweiterte Speicherklassenmodifizierer wird verwendet, um eine threadlokale Variable zu deklarieren. Für die Portable Äquivalent in C ++ 11 und höher, verwendet der [Thread_local](../cpp/storage-classes-cpp.md#thread_local) Speicherklassenbezeichner.

## <a name="syntax"></a>Syntax

```
__declspec( thread ) declarator
```

## <a name="remarks"></a>Hinweise

Threadlokaler Speicher (TLS) ist der Mechanismus, mit dem jeder Thread in einem Multithreadprozess den Speicher für threadspezifische Daten zuordnet. In den standardmäßigen Multithreadprogrammen werden Daten auf allen Threads eines angegebenen Prozesses freigegeben, während der threadlokale Speicher der Mechanismus zum Zuordnen der threadspezifischen Daten ist. Eine vollständige Erläuterung zu Threads finden Sie unter [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Deklarationen von threadlokalen Variablen verwenden, müssen [erweiterte Attributsyntax](../cpp/declspec.md) und `__declspec` Schlüsselwort mit dem **Thread** Schlüsselwort. Mit folgendem Code wird z. B. eine Ganzzahl-TLS-Variable deklariert und mit einem Wert initialisiert:

```cpp
__declspec( thread ) int tls_i = 1;  
```

Sie müssen diese Richtlinien beachten, wenn Sie threadlokale Objekte und Variablen deklarieren:

- Sie können Anwenden der **Thread** -Attribut nur auf die Klasse und Datendeklarationen und -Definitionen. **Thread** kann nicht für Funktionsdeklarationen oder-Definitionen verwendet werden.

- Die Verwendung der **Thread** Attribut beeinträchtigen möglicherweise [das verzögerte Laden](../build/reference/linker-support-for-delay-loaded-dlls.md) von DLL-Importen.

- Auf XP-Systemen **Thread** möglicherweise nicht ordnungsgemäß, wenn eine DLL __declspec(Thread)-Daten verwendet und dynamisch über LoadLibrary geladen wird.

- Sie können angeben, die **Thread** Attribut nur für Datenelemente mit statischer Speicherdauer. Hierzu zählen globale Datenobjekte (sowohl **statische** und **"extern"**), lokale statische Objekte sowie statische Datenmember von Klassen. Sie können automatische Datenobjekte mit nicht deklarieren die **Thread** Attribut.

- Verwenden Sie die **Thread** -Attribut für die Deklaration und Definition eines lokalen Threadobjekts, egal ob die Deklaration und Definition in der gleichen Datei oder in separaten Dateien auftreten.

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

- In Standard-C ist die Initialisierung eines Objekts oder einer Variablen mit einem Ausdruck zulässig, der einen Verweis auf sich selbst enthält. Dies gilt jedoch nur für Objekte, die keinen statischen Wertebereich aufweisen. Obwohl in C++ diese dynamische Objektinitialisierung mit einem Ausdruck, der einen Verweis auf sich selbst enthält, normalerweise zulässig ist, ist dieser Initialisierungstyp für lokale Threadobjekte nicht zulässig. Zum Beispiel:

    ```cpp
    // declspec_thread_3.cpp
    // compile with: /LD
    #define Thread __declspec( thread )
    int j = j;   // Okay in C++; C error
    Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
    ```

     Beachten Sie, dass eine **"sizeof"** Ausdruck, der das Objekt, das derzeit initialisiert wird, keinen Verweis auf sich selbst und in C- und C++ zulässig ist.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)  
[Schlüsselwörter](../cpp/keywords-cpp.md)  
[Threadlokaler Speicher (TLS)](../parallel/thread-local-storage-tls.md)

