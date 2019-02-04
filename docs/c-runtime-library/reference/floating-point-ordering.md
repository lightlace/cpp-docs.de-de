---
title: isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered
ms.date: 01/31/2019
f1_keywords:
- isgreater
- math/isgreater
- isgreaterequal
- math/isgreaterequal
- isless
- math/isless
- islessequal
- math/islessequal
- islessgreater
- math/islessgreater
- isunordered
- math/isunordered
helpviewer_keywords:
- isgreater function
- isgreaterequal function
- isless function
- islessequal function
- islessgreater function
- isunordered function
ms.openlocfilehash: 748360cae1dd0ee43645dee369c60c835246ed03
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703437"
---
# <a name="isgreater-isgreaterequal-isless-islessequal-islessgreater-isunordered"></a>isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered

Bestimmt die Reihenfolge Beziehung zwischen zwei Gleitkommawerten.

## <a name="syntax"></a>Syntax

```C
int isgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isgreaterequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isless(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isunordered(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */
```

```C++
template <class FloatingType1, class FloatingType2>
inline bool isgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isgreaterequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isless(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isunordered(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>Parameter

*x*, *y*<br/>
Der zu vergleichenden Gleitkommazahlen-Punktwerte.

## <a name="return-value"></a>Rückgabewert

Vergleichen in alle Vergleiche unendliche von der gleichen Anmeldebenutzeroberfläche als gleichwertig. Minus unendlich ist kleiner als jedes beliebige endlicher Wert oder plus unendlich. Plus unendlich ist größer als alle endlicher Wert oder minus unendlich. Nullen sind gleich, unabhängig von der Anmeldung. NaN-Werte sind nicht kleiner als, gleich oder größer als ein beliebiger Wert, einschließlich einer anderen NaN.

Wenn kein Argument ein NaN-Wert, die Makros, die Sortierung ist **Isgreater**, **Isgreaterequal**, **Isless**, und **Islessequal** ungleich NULL zurück Wert, wenn die angegebene Sortierung Beziehung zwischen *x* und *y* gilt. Diese Makros geben 0 zurück, wenn eine oder beide Argumente NaN-Werte sind oder die Sortierung Beziehung auf "false" festgelegt ist. Die Funktion Formulare Verhalten sich die gleiche Weise, aber zurückgeben **"true"** oder **"false"**.

Die **Islessgreater** Makro gibt einen Wert ungleich NULL zurück, wenn *x* und *y* sind keine NaN-Werte, und *x* ist entweder kleiner oder größer als *y*. Es gibt 0 zurück, wenn eine oder beide Argumente NaN-Werte sind oder wenn die Werte gleich sind. Das Formular für die Funktion verhält sich genauso, gibt jedoch **"true"** oder **"false"**.

Die **Isunordered** Makro gibt einen Wert ungleich NULL zurück, falls *x*, *y*, oder NaN-Werte. Andernfalls wird 0 (null) zurückgegeben. Das Formular für die Funktion verhält sich genauso, gibt jedoch **"true"** oder **"false"**.

## <a name="remarks"></a>Hinweise

Dieser Vergleichsvorgänge werden als Makros, die beim Kompilieren als C++ und als Inline-Vorlagenfunktionen beim Kompilieren als C++ implementiert.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|--------------|---------------------------|-------------------------------|
| **isgreater**, **isgreaterequal**, **isless**,<br/>**islessequal**, **islessgreater**, **isunordered** | \<math.h> | \<math.h> or \<cmath> |

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
