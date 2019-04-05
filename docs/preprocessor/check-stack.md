---
title: check_stack
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
ms.openlocfilehash: 49477a3b39db17047f349e341bd05c04954c964c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023373"
---
# <a name="checkstack"></a>check_stack
Weist den Compiler an, stapelüberprüfungen deaktivieren können, wenn `off` (oder `-`) angegeben wird, oder wenn stapelüberprüfungen zu deaktivieren `on` (oder `+`) angegeben ist.

## <a name="syntax"></a>Syntax

```
#pragma check_stack([ {on | off}] )
#pragma check_stack{+ | -}
```

## <a name="remarks"></a>Hinweise

Wird kein Argument angegeben ist, werden Stapelüberprüfungen gemäß der Standardeinstellung behandelt. Dieses Pragma tritt mit der ersten Funktionsdefinition in Kraft, nachdem das Pragma angezeigt wird. Stapelüberprüfungen sind weder ein Bestandteil von Makros noch von Funktionen, die inline generiert werden.

Wenn Sie ein Argument für geben nicht die **Check_stack** Pragma stapelüberprüfung das Verhalten in der Befehlszeile angegeben wird zurückgesetzt. Weitere Informationen finden Sie unter [Compilerreferenz](../build/reference/compiler-options.md). Die Interaktion der `#pragma check_stack` und [/GS](../build/reference/gs-control-stack-checking-calls.md) Option wird in der folgenden Tabelle zusammengefasst.

### <a name="using-the-checkstack-pragma"></a>Verwenden des check_stack-Pragmas

|Syntax|Kompiliert mit der<br /><br /> /Gs-Option?|Aktion|
|------------|------------------------------------|------------|
|`#pragma check_stack( )` oder<br /><br /> `#pragma check_stack`|Ja|Deaktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|
|`#pragma check_stack( )` oder<br /><br /> `#pragma check_stack`|Nein|Aktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|
|`#pragma check_stack(on)`<br /><br /> oder `#pragma check_stack +`|"Ja" oder "Nein"|Aktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|
|`#pragma check_stack(off)`<br /><br /> oder `#pragma check_stack -`|"Ja" oder "Nein"|Deaktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)