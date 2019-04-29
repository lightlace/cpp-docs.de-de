---
title: NULL-Makros und undefinierte Makros
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
ms.openlocfilehash: 0f4905473dd6914547ad6ac129d34e438992c2af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320499"
---
# <a name="null-and-undefined-macros"></a>NULL-Makros und undefinierte Makros

Null und Undefinierte Makros erweitern, um null-Zeichenfolgen, aber ein Makro definiert als null-Zeichenfolge gelten als definiert, in der Vorabverarbeitung von Ausdrücken. Geben Sie zum Definieren eines Makros als null-Zeichenfolge keine Zeichen außer Leerzeichen oder Tabstopps hinter dem Gleichheitszeichen (=) in einer Befehlszeile oder Befehlsdatei, und schließen Sie die null-Zeichenfolge oder der Definition in doppelte Anführungszeichen (""). Um ein Makro aufzuheben, verwenden Sie **! UNDEF.** Weitere Informationen finden Sie unter [Direktiven für die Makefile-Vorverarbeitung](makefile-preprocessing-directives.md).

## <a name="see-also"></a>Siehe auch

[Definieren eines NMAKE-Makros](defining-an-nmake-macro.md)
