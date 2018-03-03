---
title: /Zc:alignedNew (C ++ 17 ausgerichtetes Zuweisung) | Microsoft Docs
ms.date: 12/14/2017
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc:alignedNew
dev_langs:
- C++
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a4d6e801b258697154a4b11c7b5e468c090cc94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (C ++ 17 ausgerichtetes Zuweisung)

Aktivieren der Unterstützung für C ++ 17-ausgerichtete **neue**, dynamische speicherbelegung auf größer als der Standardwert für die maximale Größe standard ausgerichteten Typ-Grenzen ausgerichtet **max\_ausrichten\_t**.

## <a name="syntax"></a>Syntax

> **/Zc:alignedNew**[-]

## <a name="remarks"></a>Hinweise

Visual Studio, Version 15.5 kann Compiler und Library-Unterstützung für C ++ 17 standard ausgerichtetes dynamischen Arbeitsspeicher. Wenn die **/Zc:alignedNew** angegeben wird, wie z. B. eine dynamische Zuweisung `new Example;` respektiert die Ausrichtung des *Beispiel* auch wenn es größer ist `max_align_t`, der größten Ausrichtung für alle fundamentaler Typ erforderlich. Wenn die Ausrichtung des zugeordneten Typs wird nicht mehr als die von der ursprünglichen Operator garantierten **neue**, die als Wert für das vordefinierte Makro  **\_ \_STDCPP\_Standard \_Neu\_Ausrichtung\_\_**, die Anweisung `new Example;` führt zu einem Aufruf von `::operator new(size_t)` wie in C ++ 14. Wenn die Ausrichtung ist größer als  **\_ \_STDCPP\_Standard\_neu\_Ausrichtung\_\_**, stattdessen Ruft die Implementierung der Arbeitsspeicher mit `::operator new(size_t, align_val_t)`. Löschen von ausgerichtetes Typen entsprechend ruft `::operator delete(void*, align_val_t)` oder löschen Sie die Größe Signatur `::operator delete(void*, size_t, align_val_t)`.

Die **/Zc:alignedNew** Option ist nur verfügbar, wenn [/std:c ++ 17](std-specify-language-standard-version.md) oder [/std:c ++ neueste](std-specify-language-standard-version.md) aktiviert ist. Klicken Sie unter **/std:c ++ 17** oder **/std:c ++ neueste**, **/Zc:alignedNew** ist standardmäßig aktiviert, die ISO C ++ 17-standard entsprechen. Wenn der einzige Grund Operator zu implementieren **neue** und **löschen** dient zur Unterstützung von ausgerichteter Zuordnungen können Sie diesen Code im C ++ 17-Modus nicht mehr benötigen. Diese Option deaktivieren und zu den C ++ 14 Verhalten der **neue** und **löschen** Wenn **/std::c ++ 17** oder **/std:c ++ neueste** angegeben wird, Geben Sie **/Zc:alignedNew-**. Wenn Sie den Operator implementieren **neue** und **löschen** , aber Sie sind nicht bereit für die ausgerichtetes Operator implementieren **neue** und **löschen** Überladungen der `align_val_t` verwenden die **/Zc:alignedNew-** Option aus, um den Compiler und die Standardbibliothek generieren zu verhindern, dass der ausgerichtetes Überladungen aufruft.

## <a name="example"></a>Beispiel

In diesem Beispiel wird gezeigt, wie Operator **neue** and -Operator **löschen** verhält, wenn die **/Zc:alignedNew** Option festgelegt ist.

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

Diese Ausgabe ist typisch für die 32-Bit-Builds. Der Zeiger Werte variieren basierend auf, in dem die Anwendung im Arbeitsspeicher ausgeführt wird.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [nicht standardmäßigem Verhalten](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite in der **C/C++-** Ordner.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc:alignedNew** oder **/Zc:alignedNew-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/ Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)  
