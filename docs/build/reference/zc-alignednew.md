---
title: '/ Zc: alignednew (C ++ 17 ausgerichtete-Zuteilung)'
ms.date: 02/28/2018
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: 0e6cf408e56dd6e5bc262c39dda460253a32dfc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662461"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/ Zc: alignednew (C ++ 17 ausgerichtete-Zuteilung)

Aktivieren der Unterstützung für C ++ 17-über-ausgerichtete **neue**, dynamische speicherbelegung auf größer als der Standardwert für die maximale Größe standard ausgerichteten Typ-Grenzen ausgerichtet **max\_ausrichten\_t**.

## <a name="syntax"></a>Syntax

> **/ Zc: alignednew**[-]

## <a name="remarks"></a>Hinweise

Visual Studio, Version 15.5 kann Compiler und bibliotheksunterstützung für C ++ 17 standard ausgerichtete dynamische speicherbelegung. Wenn die **/Zc: alignednew** angegeben wird, wie z. B. eine dynamische Zuordnung `new Example;` respektiert die Ausrichtung des *Beispiel* selbst wenn er größer als ist `max_align_t`, der größten Ausrichtung für alle grundlegenden Typ erforderlich. Wenn die Ausrichtung des zugeordneten Typs wird nicht mehr als den, der vom ursprünglichen Operator **neue**, verfügbar als Wert für das vordefinierte Makro  **\_ \_STDCPP\_Standard \_Neu\_Ausrichtung\_\_**, die Anweisung `new Example;` führt zu einem Aufruf von `::operator new(size_t)` wie in C ++ 14. Wenn die Ausrichtung ist größer als  **\_ \_STDCPP\_Standard\_neu\_Ausrichtung\_\_**, stattdessen erhält von die Implementierung der Arbeitsspeicher mit `::operator new(size_t, align_val_t)`. Löschen von überalignierten Typen auf ähnliche Weise ruft `::operator delete(void*, align_val_t)` oder löschen Sie die Größe Signatur `::operator delete(void*, size_t, align_val_t)`.

Die **/Zc: alignednew** Option ist nur verfügbar, wenn [/Std: c ++ 17](std-specify-language-standard-version.md) oder [/Std: c ++ neueste](std-specify-language-standard-version.md) aktiviert ist. Klicken Sie unter **/Std: c ++ 17** oder **/Std: c ++ neueste**, **/Zc: alignednew** ist standardmäßig aktiviert, der ISO C ++ 17-standard entsprechen. Wenn der einzige Grund Operator implementieren **neue** und **löschen** dient zur Unterstützung von ausgerichteter Zuweisungen, Sie können diesen Code in C ++ 17-Modus nicht mehr benötigen. Diese Option deaktivieren und zu den C ++ 14 Verhalten der **neue** und **löschen** beim **/std::c ++ 17** oder **/Std: c ++ neueste** angegeben wird, Geben Sie **alignednew-erfolgt**. Wenn Sie den Operator implementieren **neue** und **löschen** , aber Sie sind nicht ausgerichteten Operator implementieren **neue** und **löschen** Überladungen, die die `align_val_t` verwenden die **alignednew-erfolgt** Option aus, um den Compiler und Standardbibliothek generieren zu verhindern, dass der ausgerichtete Überladungen aufruft. Die [/ PERMISSIVE--](permissive-standards-conformance.md) Option ändert nicht die Standardeinstellung von **/Zc: alignednew**.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie Operator **neue** and -Operator **löschen** verhält, wenn die **/Zc: alignednew** Option festgelegt ist.

```cpp
// alignedNew.cpp
// Compile by using: cl /EHsc /std:c++17 /W4 alignedNew.cpp
#include <iostream>
#include <malloc.h>
#include <new>

// "old" unaligned overloads
void* operator new(std::size_t size) {
    auto ptr = malloc(size);
    std::cout << "unaligned new(" << size << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size) {
    std::cout << "unaligned sized delete(" << ptr << ", " << size << ")\n";
    free(ptr);
}

void operator delete(void* ptr) {
    std::cout << "unaligned unsized delete(" << ptr << ")\n";
    free(ptr);
}

// "new" over-aligned overloads
void* operator new(std::size_t size, std::align_val_t align) {
    auto ptr = _aligned_malloc(size, static_cast<std::size_t>(align));
    std::cout << "aligned new(" << size << ", " <<
        static_cast<std::size_t>(align) << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size, std::align_val_t align) {
    std::cout << "aligned sized delete(" << ptr << ", " << size <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

void operator delete(void* ptr, std::align_val_t align) {
    std::cout << "aligned unsized delete(" << ptr <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

struct alignas(256) OverAligned {}; // warning C4324, structure is padded

int main() {
    delete new int;
    delete new OverAligned;
}
```

Diese Ausgabe ist typisch für 32-Bit-Builds. Der Zeiger Werte variieren basierend auf, in denen Ihre Anwendung im Arbeitsspeicher ausgeführt wird.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc: alignednew** oder **alignednew-erfolgt** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)
