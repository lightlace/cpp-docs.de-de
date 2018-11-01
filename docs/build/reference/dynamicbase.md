---
title: /DYNAMICBASE
ms.date: 06/12/2018
f1_keywords:
- /dynamicbase
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
ms.openlocfilehash: fb8bfd4f4b11d14dbbc605f4366cf1cd5446a319
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430787"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

Gibt an, ob ein ausführbares Image generiert werden, das nach dem Zufallsprinzip ein REBASE können zur Ladezeit ausgeführt werden mit der Address Space Layout Randomization (ASLR)-Funktion von Windows, die zuerst in Windows Vista verfügbar war.

## <a name="syntax"></a>Syntax

> **/ DYNAMICBASE**[**: NO**]

## <a name="remarks"></a>Hinweise

Die **/DynamicBase** Option ändert den Header einer *ausführbares Image*, eine .dll oder .exe-Datei, um anzugeben, ob die Anwendung nach dem Zufallsprinzip ein zur Ladezeit REBASE sollte und ermöglicht es virtuelle Adresse Zuordnung Randomization, das wirkt sich die virtuellen Speicheradresse des Heaps, stapeln und anderen Betriebssystem-Zuordnungen. Die **/DynamicBase** Option gilt für 32-Bit- und 64-Bit-Images. ASLR wird unter Windows Vista und späteren Betriebssystemen unterstützt. Die Option wird von älteren Betriebssystemen ignoriert.

In der Standardeinstellung **/DynamicBase** aktiviert ist. Verwenden Sie zum Deaktivieren dieser Option **/DYNAMICBASE:NO**. Die **/DynamicBase** Option ist erforderlich, damit die [/highentropyva](highentropyva-support-64-bit-aslr.md) Option aus, um die Auswirkungen haben.

## <a name="see-also"></a>Siehe auch

- [EDITBIN-Optionen](../../build/reference/editbin-options.md)
- [Windows ISV-Softwaresicherheitsmaßnahmen](https://msdn.microsoft.com/library/bb430720.aspx)