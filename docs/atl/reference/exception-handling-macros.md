---
title: Ausnahmebehandlungs-Makros
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 8afb2019e38f7548467e85d9a2c1c12c538cf744
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276247"
---
# <a name="exception-handling-macros"></a>Ausnahmebehandlungs-Makros

Diese Makros bieten Unterstützung für die Ausnahmebehandlung.

|||
|-|-|
|[_ATLCATCH](#_atlcatch)|Anweisungen zum Behandeln von Fehlern, die im zugeordneten `_ATLTRY`.|
|[_ATLCATCHALL](#_atlcatchall)|Anweisungen zum Behandeln von Fehlern, die im zugeordneten `_ATLTRY`.|
|[_ATLTRY](#_atltry)|Markiert einen geschütztes Codeabschnitt, in dem Fehler möglicherweise auftreten können.|

## <a name="requirements"></a>Anforderungen:

**Header:** atldef.h

##  <a name="_atlcatch"></a>  _ATLCATCH

Anweisungen zum Behandeln von Fehlern, die im zugeordneten `_ATLTRY`.

```
_ATLCATCH(e)
```

### <a name="parameters"></a>Parameter

*e*<br/>
Die Ausnahme abgefangen.

### <a name="remarks"></a>Hinweise

Zusammen mit `_ATLTRY`. Löst in C++ [catch (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) für eine bestimmte Art von C++-Ausnahmen zu behandeln.

##  <a name="_atlcatchall"></a>  _ATLCATCHALL

Anweisungen zum Behandeln von Fehlern, die im zugeordneten `_ATLTRY`.

```
_ATLCATCHALL
```

### <a name="remarks"></a>Hinweise

Zusammen mit `_ATLTRY`. Löst in C++ [catch(...) ](../../cpp/try-throw-and-catch-statements-cpp.md) für alle Arten von C++-Ausnahmen zu behandeln.

##  <a name="_atltry"></a>  _ATLTRY

Markiert einen geschütztes Codeabschnitt, in dem Fehler möglicherweise auftreten können.

```
_ATLTRY
```

### <a name="remarks"></a>Hinweise

Zusammen mit [_ATLCATCH](#_atlcatch) oder [_ATLCATCHALL](#_atlcatchall). Löst in der C++-Symbol [versuchen](../../cpp/try-throw-and-catch-statements-cpp.md).

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
