---
title: Dateipositionsfehler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8def11317548bfd6e70badab4563891c1b6f864d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031907"
---
# <a name="file-position-errors"></a>Dateipositionsfehler

**ANSI 4.9.9.1, 4.9.9.4** Der Wert, auf den das Makro `errno` bei einem Fehler durch die `fgetpos`- oder `ftell`-Funktion festgelegt wird

Wenn `fgetpos` oder `ftell` fehlschlägt, wird `errno` auf die Manifestkonstante `EINVAL` festgelegt, wenn die Position ungültig ist, oder auf `EBADF`, wenn die Dateinummer ungültig ist. Die Konstanten sind in ERRNO.H definiert.

## <a name="see-also"></a>Siehe auch

[Bibliotheksfunktionen](../c-language/library-functions.md)
