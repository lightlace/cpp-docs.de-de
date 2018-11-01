---
title: 'NMAKE: Schwerwiegender Fehler U1001'
ms.date: 11/04/2016
f1_keywords:
- U1001
helpviewer_keywords:
- U1001
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
ms.openlocfilehash: bfe2edf9c57eda073826a8c161ae0c358f3a6232
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662240"
---
# <a name="nmake-fatal-error-u1001"></a>NMAKE: Schwerwiegender Fehler U1001

Syntaxfehler: Ungültiges Zeichen 'Zeichen' in Makro

Das angegebene Zeichen wird angezeigt, in einem Makro ist jedoch kein Buchstabe, eine Zahl oder ein Unterstrich.

Dieser Fehler kann durch einen fehlenden Doppelpunkt in einer makroerweiterung verursacht werden:

```
syntax error : illegal character '=' in macro
```