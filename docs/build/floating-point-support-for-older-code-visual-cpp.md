---
title: Gleitkommaunterstützung für älteren Code (Visual C++)
ms.date: 11/04/2016
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
ms.openlocfilehash: 2340a4d136dee3438a47ce06793ed9274035250d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509642"
---
# <a name="floating-point-support-for-older-code-visual-c"></a>Gleitkommaunterstützung für älteren Code (Visual C++)

MMX und Gleitkommastapel Register (MM0-MM7/ST0-ST7) werden für Kontextwechsel beibehalten.  Es gibt keine explizite Aufrufkonvention für diese Register.  Die Verwendung von diese Register wird im Kernelmoduscode streng untersagt.

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)