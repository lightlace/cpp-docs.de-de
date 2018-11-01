---
title: 'Ressourcencompiler: Warnung RW4004'
ms.date: 11/04/2016
f1_keywords:
- RW4004
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
ms.openlocfilehash: bafd1084a665fc656fe184064a48e5fffc61c957
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485643"
---
# <a name="resource-compiler-warning-rw4004"></a>Ressourcencompiler: Warnung RW4004

ASCII-Zeichen entspricht nicht dem virtuellem Tastencode

Für den virtueller Tastencode in einer VIRTKEY-Zugriffstaste wurde ein Zeichenfolgenliteral verwendet.

Trotz der Warnung können Sie den Vorgang fortsetzen. Sie informiert Sie jedoch darüber, dass die generierten Zugriffstasten möglicherweise nicht mit der Zeichenfolge übereinstimmen, die Sie angegeben haben. (VIRTKEY-Zugriffstasten verwenden andere Tastencodes als ASCII-Zugriffstasten.)

Obwohl Zeichenfolgenliterale syntaktisch zulässig sind, können Sie nur sicherstellen, dass Sie die Zugriffstaste sollen erhalten, mithilfe der **VK_\* #define** Werte in Windows.h dar.