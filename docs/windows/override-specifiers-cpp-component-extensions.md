---
title: Überschreibungsspezifizierer (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- override specifiers, Visual C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 71cafe3d73204b6a318e731d0a95f2dfcc73fa5a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600122"
---
# <a name="override-specifiers--c-component-extensions"></a>Überschreibungsspezifizierer (Komponentenerweiterungen für C++)

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

[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)