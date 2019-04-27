---
title: /HIGHENTROPYVA
ms.date: 06/12/2018
f1_keywords:
- /HIGHENTROPYVA
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
ms.openlocfilehash: 90d3c868eaab85e3b1a2a416c9aa14b0e27ec8f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270223"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

Gibt an, ob das ausführbare Image 64-bit-ASLR mit hoher Entropie unterstützt.

## <a name="syntax"></a>Syntax

> **/HIGHENTROPYVA**[**:NO**]

## <a name="remarks"></a>Hinweise

Diese Option ändert den Header einer *ausführbares Image*, eine DLL-Datei oder der .exe-Datei, um anzugeben, ob ASLR mit 64-Bit-Adressen unterstützt wird. Wenn diese Option auf einer ausführbaren Datei und allen Modulen festgelegt wird, von denen sie abhängt, kann ein 64-Bit-ASLR unterstützendes Betriebssystem für die Segmente des ausführbaren Images zur Ladezeit ein Rebase ausführen, indem zufällige Adressen in einem virtuellen 64-Bit-Adressbereich verwendet werden. Aufgrund dieses großen Adressbereichs ist es für einen Angreifer schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.

Standardmäßig ermöglicht der Linker **/highentropyva** für ausführbare 64-Bit-Images. Diese Option erfordert [/LARGEADDRESSAWARE](largeaddressaware.md), die auch für 64-Bit-Images standardmäßig aktiviert ist. **/ HIGHENTROPYVA** gilt nicht für ausführbare 32-Bit-Images, in denen die Option wird ignoriert. Um diese Option explizit zu deaktivieren, verwenden **/HIGHENTROPYVA:NO**. Für diese Option, um die Auswirkungen, haben die [/DynamicBase](dynamicbase.md) Option muss auch festgelegt werden.

## <a name="see-also"></a>Siehe auch

- [EDITBIN-Optionen](editbin-options.md)
- [/DYNAMICBASE](dynamicbase.md)
- [Windows ISV-Softwaresicherheitsmaßnahmen](https://msdn.microsoft.com/library/bb430720.aspx)
