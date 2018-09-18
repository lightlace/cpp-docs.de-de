---
title: 'NMAKE: Schwerwiegender Fehler U1001 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1001
dev_langs:
- C++
helpviewer_keywords:
- U1001
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4e465af5b4fa22c5f0ba5a9e01ebde0a7ee89e9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068142"
---
# <a name="nmake-fatal-error-u1001"></a>NMAKE: Schwerwiegender Fehler U1001

Syntaxfehler: Ungültiges Zeichen 'Zeichen' in Makro

Das angegebene Zeichen wird angezeigt, in einem Makro ist jedoch kein Buchstabe, eine Zahl oder ein Unterstrich.

Dieser Fehler kann durch einen fehlenden Doppelpunkt in einer makroerweiterung verursacht werden:

```
syntax error : illegal character '=' in macro
```