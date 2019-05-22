---
title: /Zc:alignedNew (C++17-Zuteilung mit erweiterter Ausrichtung)
ms.date: 05/18/2019
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: dfcc4982e1b5f67b5a01d5a0d09d4fd9279deacf
ms.sourcegitcommit: 61121faf879cc581a4d39e4baccabf7cf1f673a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934184"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (C++17-Zuteilung mit erweiterter Ausrichtung)

Ermöglichen Sie die Unterstützung für den C++17-Operator **new** mit erweiterter Ausrichtung und dynamischer Speicherzuteilung, ausgerichtet an Grenzen jenseits des Standards des maximalgroßen Ausrichtungstyps **max\_align\_t**.

## <a name="syntax"></a>Syntax

> **/Zc:alignedNew**\[-]

## <a name="remarks"></a>Anmerkungen

Der MSVC-Compiler und die -Bibliothek unterstützten die dynamische Speicherzuteilung für C++17 mit erweiterter Ausrichtung. Wenn die Option **/Zc:alignedNew** angegeben ist, respektieren dynamische Zuteilungen wie `new Example;` die Ausrichtung von *Example*. Dies ist sogar dann der Fall, wenn der Wert für die Ausrichtung größer als `max_align_t` ist (die größte Ausrichtung für jeden grundlegenden Typ). Wenn die Ausrichtung des zugeteilten Typs den Wert für die vom ursprünglichen Operator **new** (verfügbar als der Wert des vordefinierten Makros **\_\_STDCPP\_DEFAULT\_NEW\_ALIGNMENT\_\_**) garantierte Ausrichtung nicht überschreitet, wird genauso wie in C++14 als Ergebnis der die Anweisung `new Example;` `::operator new(size_t)` aufgerufen. Wenn die Ausrichtung größer als **\_\_STDCPP\_DEFAULT\_NEW\_ALIGNMENT\_\_** ist, wird durch die Implementierung stattdessen mithilfe von `::operator new(size_t, align_val_t)` der Speicher abgerufen. Ebenso werden `::operator delete(void*, align_val_t)` oder die Löschsignatur mit angegebener Größe (`::operator delete(void*, size_t, align_val_t)`) aufgerufen, wenn Typen mit erweiterter Ausrichtung gelöscht werden.

Die Option **/Zc:alignedNew** ist nur verfügbar, wenn [/std:c++17](std-specify-language-standard-version.md) oder [/std:c++latest](std-specify-language-standard-version.md) aktiviert ist. Unter **/std:c++17** oder **/std:c++latest** wird gemäß dem ISO-Standard für C++17 standardmäßig **/Zc:alignedNew** aktiviert. Wenn Sie die Operatoren **new** und **delete** nur implementieren, um Zuteilungen mit erweiterter Ausrichtung zu unterstützen, benötigen Sie diesen Code im Modus „C++17“ möglicherweise nicht mehr. Geben Sie **/Zc:alignedNew-** an, um diese Option zu deaktivieren und das C++14-Verhalten von **new** und **delete** wieder herzustellen, wenn Sie **/std::c++17** oder **/std:c++latest** verwenden. Wenn Sie die Operatoren **new** und **delete** implementieren, aber noch nicht die Operatorüberladungen mit erweiterter Ausrichtung **new** und **delete** implementieren möchten, die den Parameter `align_val_t` aufweisen, verwenden Sie die Option **/Zc:alignedNew-**, um zu vermeiden, dass der Compiler und die Standardbibliothek die Überladungen mit erweiterter Ausrichtung aufrufen. Die Standardeinstellung von **/Zc:alignedNew** wird durch die Option [/permissive-](permissive-standards-conformance.md) nicht geändert.

**/Zc:alignedNew** wird ab Visual Studio 2017, Version 15.5 unterstützt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird das Verhalten der Operatoren **new** und **delete** gezeigt, wenn die Option **/Zc:alignedNew** festgelegt ist.

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

Diese Ausgabe ist typisch für 32-Bit-Builds. Die Zeigerwerte variieren je nach Ausführungsort Ihrer Anwendung im Speicher.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nicht dem Standard entsprechendes Verhalten](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++** > **Befehlszeile**.

1. Ändern Sie die Eigenschaft **Weitere Optionen**, um **/Zc:alignedNew** oder **/Zc:alignedNew-** hinzuzufügen, und klicken Sie dann auf **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](zc-conformance.md)
