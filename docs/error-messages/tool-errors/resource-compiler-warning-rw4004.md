---
title: 'Ressourcencompiler: Warnung RW4004 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW4004
dev_langs:
- C++
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33305f1f86c0cc1722e4a235ec27927f6e70675f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095988"
---
# <a name="resource-compiler-warning-rw4004"></a>Ressourcencompiler: Warnung RW4004

ASCII-Zeichen entspricht nicht dem virtuellem Tastencode

Für den virtueller Tastencode in einer VIRTKEY-Zugriffstaste wurde ein Zeichenfolgenliteral verwendet.

Trotz der Warnung können Sie den Vorgang fortsetzen. Sie informiert Sie jedoch darüber, dass die generierten Zugriffstasten möglicherweise nicht mit der Zeichenfolge übereinstimmen, die Sie angegeben haben. (VIRTKEY-Zugriffstasten verwenden andere Tastencodes als ASCII-Zugriffstasten.)

Obwohl Zeichenfolgenliterale syntaktisch zulässig sind, können Sie nur sicherstellen, dass Sie die Zugriffstaste sollen erhalten, mithilfe der **VK_\* #define** Werte in Windows.h dar.