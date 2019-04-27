---
title: '&lt;filesystem&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::operator==
- FILESYSTEM/std::experimental::filesystem::operator!=
- FILESYSTEM/std::experimental::filesystem::operator<
- FILESYSTEM/std::experimental::filesystem::operator<=
- FILESYSTEM/std::experimental::filesystem::operator>
- FILESYSTEM/std::experimental::filesystem::operator>=
- FILESYSTEM/std::experimental::filesystem::operator/
- FILESYSTEM/std::experimental::filesystem::operator<<
- FILESYSTEM/std::experimental::filesystem::operator>>
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
ms.openlocfilehash: 378e5d7b8b36aa9b891a87662d432a451ac6bafe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159898"
---
# <a name="ltfilesystemgt-operators"></a>&lt;filesystem&gt;-Operatoren

Die Operatoren führen einen lexikalischen Vergleich von zwei Pfaden als Zeichenfolgen aus. Verwenden der `equivalent` Funktion, um zu bestimmen, ob zwei Pfade (beispielsweise ein relativer Pfad und ein absoluter Pfad) auf dieselbe Datei oder dasselbe Verzeichnis auf dem Datenträger verweisen.

Weitere Informationen finden Sie unter [Dateisystemnavigation](../standard-library/file-system-navigation.md).

## <a name="operator"></a>operator==

```cpp
bool operator==(const path& left, const path& right) noexcept;
```

Die Funktion gibt „left.native() == right.native()“ zurück.

## <a name="operator"></a>Operator!=

```cpp
bool operator!=(const path& left, const path& right) noexcept;
```

Die Funktion gibt „!(left == right)“ zurück.

## <a name="operator"></a>Operator <

```cpp
bool operator<(const path& left, const path& right) noexcept;
```

Die Funktion gibt „left.native() < right.native()“ zurück.

## <a name="operator"></a>Operator <=

```cpp
bool operator<=(const path& left, const path& right) noexcept;
```

Die Funktion gibt „!(right \< left)“ zurück.

## <a name="operator"></a>Operator >

```cpp
bool operator>(const path& left, const path& right) noexcept;
```

Die Funktion gibt „right \< left“ zurück.

## <a name="operator"></a>Operator >=

```cpp
bool operator>=(const path& left, const path& right) noexcept;
```

Die Funktion gibt „!(left < right)“ zurück.

## <a name="operator"></a>operator/

```cpp
path operator/(const path& left, const path& right);
```

Die Funktion führt Folgendes aus:

```cpp
basic_string<Elem, Traits> str;
path ans = left;
return (ans /= right);
```

## <a name="operator"></a>Operator <<

```cpp
template <class Elem, class Traits>
basic_ostream<Elem, Traits>& operator<<(basic_ostream<Elem, Traits>& os, const path& pval);
```

Die Funktion gibt „os << pval.string\<Elem, Traits>()“ zurück.

## <a name="operator"></a>Operator >>

```cpp
template <class Elem, class Traits>
basic_istream<Elem, Traits>& operator<<(basic_istream<Elem, Traits>& is, const path& pval);
```

Die Funktion führt Folgendes aus:

```cpp
basic_string<Elem, Traits> str;
is>> str;
pval = str;
return (is);
```

## <a name="see-also"></a>Siehe auch

[Path-Klasse (C++-Standardbibliothek)](../standard-library/path-class.md)<br/>
[Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
