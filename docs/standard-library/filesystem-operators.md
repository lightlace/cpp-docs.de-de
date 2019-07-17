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
ms.openlocfilehash: 819c91e707e50a190aa58eda62f8e07f3451b033
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240731"
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
