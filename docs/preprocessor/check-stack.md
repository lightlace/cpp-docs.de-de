---
title: check_stack-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
ms.openlocfilehash: 4c976692ec36cedcb73825ee0cc7093736a3a3dc
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216136"
---
# <a name="check_stack-pragma"></a>check_stack-Pragma

Weist den Compiler an, Stapel Überprüfungen zu deaktivieren , wenn off **-** (oder) angegeben wird, oder um Stapel Überprüfungen zu aktivieren, **+** Wenn **on** (oder) angegeben ist.

## <a name="syntax"></a>Syntax

> **#pragma check_stack (** [{ **on** | **Off** }] **)** \
> **#pragma check_stack** { **+**  |  **-** }

## <a name="remarks"></a>Hinweise

Dieses Pragma tritt mit der ersten Funktionsdefinition in Kraft, nachdem das Pragma angezeigt wird. Stapelüberprüfungen sind weder ein Bestandteil von Makros noch von Funktionen, die inline generiert werden.

Wenn Sie kein Argument für das **check_stack** -Pragma angeben, wird die Stapel Überprüfung auf das in der Befehlszeile angegebene Verhalten zurückgesetzt. Weitere Informationen finden Sie unter [Compileroptionen](../build/reference/compiler-options.md). Die Interaktion `#pragma check_stack` zwischen der-Option und der [/GS](../build/reference/gs-control-stack-checking-calls.md) -Option ist in der folgenden Tabelle zusammengefasst.

### <a name="using-the-check_stack-pragma"></a>Verwenden des check_stack-Pragmas

|Syntax|Kompiliert mit der<br /><br /> /Gs-Option?|Aktion|
|------------|------------------------------------|------------|
|`#pragma check_stack( )` oder<br /><br /> `#pragma check_stack`|Ja|Deaktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|
|`#pragma check_stack( )` oder<br /><br /> `#pragma check_stack`|Nein|Aktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|
|`#pragma check_stack(on)`<br /><br /> noch`#pragma check_stack +`|"Ja" oder "Nein"|Aktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|
|`#pragma check_stack(off)`<br /><br /> noch`#pragma check_stack -`|"Ja" oder "Nein"|Deaktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
