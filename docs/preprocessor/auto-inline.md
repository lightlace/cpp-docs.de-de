---
title: auto_inline-Pragma
ms.date: 08/29/2019
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
ms.openlocfilehash: 59cda8cb73196215318c9570a5c067786284afaa
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216314"
---
# <a name="auto_inline-pragma"></a>auto_inline-Pragma

Schließt alle Funktionen aus, die innerhalb des Bereichs definiert sind, in dem **Off** angegeben wird, der als Kandidaten für die automatische Inline Erweiterung angesehen wird.

## <a name="syntax"></a>Syntax

> **#pragma auto_inline (** [{ **on** | **Off** }] **)**

## <a name="remarks"></a>Hinweise

Um das **auto_inline** -Pragma zu verwenden, platzieren Sie es vor und unmittelbar nach und nicht in einer Funktionsdefinition. Das Pragma tritt in Kraft, sobald die erste Funktionsdefinition nach dem Pragma sichtbar ist.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
