---
title: '&lt;cstddef&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 15d13a3af35cb41950df8aeba0c86d779e701ddb
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244449"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

Schließt den standard C-bibliotheksheader \<stddef.h > und fügt die verknüpften Namen zum die `std` Namespace. Einschließen dieses Headers wird sichergestellt, dass die Namen deklariert, mit externer Bindung im standard C-bibliotheksheader, in deklariert werden der `std` Namespace.

> [!NOTE]
> \<Cstddef > enthält Typ **Byte** und keine Typ **"wchar_t"** .

## <a name="syntax"></a>Syntax

```cpp
#include <cstddef>
```

## <a name="namespace-and-macros"></a>Namespace und Makros

```cpp
namespace std {
    using ptrdiff_t = see definition;
    using size_t = see definition;
    using max_align_t = see definition;
    using nullptr_t = decltype(nullptr);
}

#define NULL  // an implementation-defined null pointer constant
#define offsetof(type, member-designator)
```

### <a name="parameters"></a>Parameter

*ptrdiff_t*\
Eine implementierungsdefinierte ganzzahliger Typ mit Vorzeichen, die die Differenz zwischen zwei Indizes in einem Arrayobjekt enthalten kann.

*"size_t"* \
Eine Implementierung definierten Ganzzahltyp ohne Vorzeichen, der groß genug für die Größe in Bytes eines beliebigen Objekts enthalten ist.

*max_align_t*\
Ein POD-Typ, dessen ausrichtungsanforderung ist mindestens so groß wie mit jeder skalaren Typ; deren ausrichtungsanforderung ist in jedem Kontext unterstützt.

*nullptr_t*\
Ein Synonym für den Typ des eine **"nullptr"** Ausdruck. Obwohl eine **"nullptr"** Adresse kann nicht erstellt werden, wird die Adresse eines anderen *Nullptr_t* Objekt, das einen l-Wert erstellt werden kann.

## <a name="byte-class"></a>Byte-Klasse

```cpp
enum class byte : unsigned char {};

template <class IntType>
    constexpr byte& operator<<=(byte& b, IntType shift) noexcept;
    constexpr byte operator<<(byte b, IntType shift) noexcept;
    constexpr byte& operator>>=(byte& b, IntType shift) noexcept;
    constexpr byte operator>>(byte b, IntType shift) noexcept;

constexpr byte& operator|=(byte& left, byte right) noexcept;
constexpr byte operator|(byte left, byte right) noexcept;
constexpr byte& operator&=(byte& left, byte right) noexcept;
constexpr byte operator&(byte left, byte right) noexcept;
constexpr byte& operator^=(byte& left, byte right) noexcept;
constexpr byte operator^(byte left, byte right) noexcept;
constexpr byte operator~(byte b) noexcept;

template <class IntType>
    IntType to_integer(byte b) noexcept;
```

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
