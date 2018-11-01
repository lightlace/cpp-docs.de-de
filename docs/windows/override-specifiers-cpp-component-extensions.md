---
title: Überschreibungsspezifizierer (C++ / CLI und C++ / CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
ms.openlocfilehash: 9d839b9530cff144cda7897b0c96af48c14454a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639854"
---
# <a name="override-specifiers--ccli-and-ccx"></a>Überschreibungsspezifizierer (C++ / CLI und C++ / CX)

*Überschreibungsspezifizierer* ändern wie geerbte Typen und Member von geerbten Typen, die in abgeleiteten Typen Verhalten.

## <a name="all-runtimes"></a>Alle Laufzeiten

### <a name="remarks"></a>Hinweise

Weitere Informationen zu Überschreibungsspezifizierern finden Sie unter:

- [abstract](../windows/abstract-cpp-component-extensions.md)

- [New (neuer Slot in Vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)

- [override](../windows/override-cpp-component-extensions.md)

- [sealed](../windows/sealed-cpp-component-extensions.md)

- [Überschreibungsspezifizierer und Native Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)

**abstrakte** und **versiegelten** sind auch in Typdeklarationen, gültig, in dem sie fungieren nicht als Überschreibungsspezifizierer auftreten.

Weitere Informationen zu den Funktionen der Basisklasse explizit überschrieben, finden Sie unter [explizite Überschreibungen](../windows/explicit-overrides-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows-Runtime

(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows-Runtime gelten.)

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Common Language Runtime gelten.)

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)