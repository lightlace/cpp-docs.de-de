---
title: '&lt;cstddef&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 87d268977ee46112fedce517e66a9e68071863db
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457571"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

Schließt den C-Standard Bibliotheks \<Header STDDEF. h > ein und fügt zugeordnete `std` Namen zum-Namespace hinzu. Durch einschließen dieses Headers wird sichergestellt, dass die mit externer Verknüpfung im C-Standard Bibliotheks Header deklarierten `std` Namen im-Namespace deklariert werden.

> [!NOTE]
> \<cstddef > enthält den Typ " **Byte** " und enthält nicht den Typ " **wchar_t**".

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
Ein von der Implementierung definierter ganzzahliger Typ mit Vorzeichen, der den Unterschied zwischen zwei Indizes in einem Array Objekt enthalten kann.

*size_t*\
Ein von der Implementierung definierter ganzzahliger Typ ohne Vorzeichen, der groß genug ist, um die Größe eines beliebigen Objekts in Bytes zu enthalten.

*max_align_t*\
Ein POD-Typ, dessen Ausrichtungs Anforderung mindestens so groß wie jeder skalare Typ ist und dessen Ausrichtungs Anforderung in jedem Kontext unterstützt wird.

*nullptr_t*\
Ein Synonym für den Typ eines **nullptr** -Ausdrucks. Obwohl eine **nullptr** -Adresse nicht verwendet werden kann, kann die Adresse eines anderen *nullptr_t* -Objekts, das ein Lvalue ist, übernommen werden.

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

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Übersicht über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
