---
title: 'SafeInt:: SafeInt | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de318ab79638f63fae98856987340ad62534f695
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721344"
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt

Erstellt eine **SafeInt** Objekt.

## <a name="syntax"></a>Syntax

```cpp
SafeInt() throw

SafeInt (
   const T& i
) throw ()

SafeInt (
   bool b
) throw ()

template <typename U>
SafeInt (
   const SafeInt <U, E>& u
)

I template <typename U>
SafeInt (
   const U& i
)  
```

### <a name="parameters"></a>Parameter

*i*<br/>
[in] Der Wert für die neue **SafeInt** Objekt. Dabei muss es sich um einen Parameter vom Typ T oder U, je nach den Konstruktor handeln.

*b*<br/>
[in] Der boolesche Wert für die neue **SafeInt** Objekt.

*u*<br/>
[in] Ein **SafeInt** u Die neue **SafeInt** Objekt hat den gleichen Wert wie *u*, aber vom Typ "t".

U den Typ der Daten in die **SafeInt**. Dies kann entweder ein boolescher Wert, Zeichen oder ganze Zahl sein. Wenn sie ein ganzzahliger Typ ist, es kann sein mit oder ohne Vorzeichen und zwischen 8 und 64-Bit sein.

## <a name="remarks"></a>Hinweise

Weitere Informationen zu den Vorlagentypen `T` und `E`, finden Sie unter [SafeInt-Klasse](../windows/safeint-class.md).

Der Eingabeparameter für den Konstruktor *ich* oder *u*, muss ein boolescher Wert, Zeichen oder Integer-Typ sein. Wenn es sich um einen anderen Typ des Parameters ist die **SafeInt** -Klasse ruft ["static_assert"](../cpp/static-assert.md) an, dass ein ungültiger Eingabeparameter.

Die Konstruktoren, mit denen den Vorlagentyp `U` automatisch in den vom angegebenen Typ konvertieren den Eingabeparameter `T`. Die **SafeInt** Klasse konvertiert die Daten ohne Verlust von Daten. Er meldet sich an den Fehlerhandler `E` wenn er die Daten in den Typ konvertieren kann `T` ohne Datenverlust.

Bei der Erstellung einer **SafeInt** in einen booleschen Parameter, müssen Sie den Wert sofort zu initialisieren. Sie können nicht erstellt werden ein **SafeInt** mithilfe des Codes `SafeInt<bool> sb;`. Dadurch wird einen Compilerfehler generiert.

## <a name="requirements"></a>Anforderungen

**Header:** safeint.h

**Namespace:** MSL:: Utilities

## <a name="see-also"></a>Siehe auch

[SafeInt-Bibliothek](../windows/safeint-library.md)  
[SafeInt-Klasse](../windows/safeint-class.md)  
[SafeIntException-Klasse](../windows/safeintexception-class.md)