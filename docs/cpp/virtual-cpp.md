---
title: virtual (C++)
ms.date: 11/04/2016
f1_keywords:
- virtual_cpp
- virtual
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
ms.openlocfilehash: f68bd2e500ebe16c43ef6c3d7a5aede26421b27d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605061"
---
# <a name="virtual-c"></a>virtual (C++)

Die **virtuellen** -Schlüsselwort deklariert eine virtuelle Funktion oder eine virtuelle Basisklasse.

## <a name="syntax"></a>Syntax

```
virtual [type-specifiers] member-function-declarator
virtual [access-specifier] base-class-name
```

#### <a name="parameters"></a>Parameter

*Typspezifizierer*<br/>
Gibt den Rückgabetyp der virtuellen Memberfunktion an.

*Member der funktionsdeklarator*<br/>
Deklariert eine Memberfunktion.

*Zugriffsspezifizierer*<br/>
Definiert die Ebene des Zugriffs auf die Basisklasse, **öffentliche**, **geschützt** oder **private**. Kann vor oder nach dem Auftreten der **virtuellen** Schlüsselwort.

*Basis-Class-name*<br/>
Identifiziert einen zuvor deklarierten Klassentyp.

## <a name="remarks"></a>Hinweise

Finden Sie unter [virtuelle Funktionen](../cpp/virtual-functions.md) für Weitere Informationen.

Siehe auch die folgenden Schlüsselwörter: [Klasse](../cpp/class-cpp.md), [private](../cpp/private-cpp.md), [öffentliche](../cpp/public-cpp.md), und [geschützt](../cpp/protected-cpp.md).

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)