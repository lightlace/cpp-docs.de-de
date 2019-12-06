---
title: Veraltete Aufrufkonventionen
ms.date: 11/04/2016
f1_keywords:
- __fortran
- __pascal
- __syscall
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
ms.openlocfilehash: 7f059afe02cbbad77920fd8c4a0e6cb7c958e992
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857358"
---
# <a name="obsolete-calling-conventions"></a>Veraltete Aufrufkonventionen

**Microsoft-spezifisch**

Die **__pascal**-, **__fortran**-und **__syscall** Aufruf Konventionen werden nicht mehr unterstützt. Sie können ihre Funktionalität emulieren, indem Sie eine der unterstützten Aufrufkonventionen und geeignete Linkeroptionen verwenden.

\<Windows. h > unterstützt jetzt das WinAPI-Makro, das in die entsprechende Aufruf Konvention für das Ziel übersetzt. Verwenden Sie WinAPI, wenn Sie zuvor Pascal oder **__far \__pascal**verwendet haben.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)