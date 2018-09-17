---
title: Gleitkommaunterstützung für älteren Code (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7285325bf1a934afcef337da318d019ec6fe375c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706809"
---
# <a name="floating-point-support-for-older-code-visual-c"></a>Gleitkommaunterstützung für älteren Code (Visual C++)

MMX und Gleitkommastapel Register (MM0-MM7/ST0-ST7) werden für Kontextwechsel beibehalten.  Es gibt keine explizite Aufrufkonvention für diese Register.  Die Verwendung von diese Register wird im Kernelmoduscode streng untersagt.

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)