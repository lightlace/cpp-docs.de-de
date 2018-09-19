---
title: Mithilfe von "atexit" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- atexit
dev_langs:
- C++
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d5164394853d2ac4f18efc94863b8fc3fa5ba78
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053127"
---
# <a name="using-atexit"></a>Verwenden von "atexit"

Mit der [von "atexit"](../c-runtime-library/reference/atexit.md) -Funktion, Sie können angeben, eine Beendigung der Verarbeitung-Funktion, die vor der Beendigung des Programms ausgeführt wird. Keine globalen statischen Objekts vor dem Aufruf von initialisiert **von "atexit"** werden vor der Ausführung der Funktion für die Beendigung der Verarbeitung zerstört.

## <a name="see-also"></a>Siehe auch

[Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)