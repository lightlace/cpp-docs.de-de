---
title: Makros für die Ausnahmebehandlung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
dev_langs:
- C++
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b503e36dfe04eaa3180809033187957ff8d970a0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766814"
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

*e*  
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
