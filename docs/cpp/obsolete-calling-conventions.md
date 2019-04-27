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
ms.openlocfilehash: 86c75c779158d9f191dd015410cf16c9ce25690d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245022"
---
# <a name="obsolete-calling-conventions"></a>Veraltete Aufrufkonventionen

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Die **__pascal**, **__fortran**, und **__syscall** Aufrufkonventionen werden nicht mehr unterstützt. Sie können ihre Funktionalität emulieren, indem Sie eine der unterstützten Aufrufkonventionen und geeignete Linkeroptionen verwenden.

\<Windows.h > unterstützt jetzt das WINAPI-Makro, das in die entsprechende Aufrufkonvention für das Ziel übersetzt. Verwenden Sie WINAPI, in dem Sie zuvor Pascal-SCHREIBWEISE verwendet, oder **__far \__pascal**.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)