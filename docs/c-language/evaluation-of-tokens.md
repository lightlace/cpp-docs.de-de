---
title: Auswertung von Tokens | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d5c79ac043b2131df7a876f2de63922c45c9ead
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035278"
---
# <a name="evaluation-of-tokens"></a>Auswertung von Tokens

Wenn der Compiler Token interpretiert, schließt er so viele Zeichen wie möglich in einem einzelnen Token ein, bevor er mit dem nächsten Token fortfährt. Aufgrund dieses Verhaltens interpretiert der Compiler möglicherweise die Token nicht wie beabsichtigt, wenn sie nicht ordnungsgemäß durch Leerzeichen getrennt werden. Betrachten Sie hierzu den folgenden Ausdruck:

```
i+++j
```

In diesem Beispiel erstellt der Compiler zunächst den längsten möglichen Operator (`++`) aus den drei Pluszeichen, dann verarbeitet er das verbleibende Pluszeichen als Addition-Operator (`+`). Daher wird der Ausdruck als `(i++) + (j)` und nicht als `(i) + (++j)` interpretiert. Verwenden Sie in diesem und ähnlichen Fällen Leerzeichen und Klammern, um Mehrdeutigkeiten zu vermeiden und eine ordnungsgemäße Ausdrucksbewertung sicherzustellen.

**Microsoft-spezifisch**

Der C-Compiler behandelt ein STRG+Z-Zeichen als Dateiendeindikator. Er ignoriert jeden Text nach STRG+Z.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[C-Tokens](../c-language/c-tokens.md)