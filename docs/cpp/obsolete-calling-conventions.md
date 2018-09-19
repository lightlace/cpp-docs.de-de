---
title: Veraltete Aufrufkonventionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs:
- C++
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eec6f8370103ed0256471c009d6e97cc693a1cd7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071340"
---
# <a name="obsolete-calling-conventions"></a>Veraltete Aufrufkonventionen

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Die **__pascal**, **__fortran**, und **__syscall** Aufrufkonventionen werden nicht mehr unterstützt. Sie können ihre Funktionalität emulieren, indem Sie eine der unterstützten Aufrufkonventionen und geeignete Linkeroptionen verwenden.

\<Windows.h > unterstützt jetzt das WINAPI-Makro, das in die entsprechende Aufrufkonvention für das Ziel übersetzt. Verwenden Sie WINAPI, in dem Sie zuvor Pascal-SCHREIBWEISE verwendet, oder **__far \__pascal**.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)