---
title: Überschreibungsspezifizierer (C++ / CLI und C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0620bc7045dcb312667cfdfe670e1f19b0545cf2
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49327463"
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

[Komponentenerweiterungen für .NET- und UWP](../windows/component-extensions-for-runtime-platforms.md)