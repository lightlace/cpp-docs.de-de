---
title: Compilerfehler C3552 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3552
dev_langs:
- C++
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd9f7ae37500e115fa33fa61298cab800c88f9c7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081259"
---
# <a name="compiler-error-c3552"></a>Compilerfehler C3552

"Typname": Ein spät angegebener Rückgabetyp darf nicht "auto" enthalten.

Wenn Sie das `auto` -Schlüsselwort als Platzhalter für den Rückgabetyp einer Funktion verwenden, müssen Sie einen spät angegebenen Rückgabetyp angeben. Allerdings können Sie kein weiteres `auto` -Schlüsselwort verwenden, um den spät angegebenen Rückgabetyp anzugeben. Im folgenden Codefragment wird beispielsweise der Fehler C3552 verursacht.

`auto myFunction->auto; // C3552`