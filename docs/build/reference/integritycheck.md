---
title: /INTEGRITYCHECK
ms.date: 12/28/2017
f1_keywords:
- /INTEGRITYCHECK
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.openlocfilehash: b3f6622e3628db53c363b239c59accd94f708ab0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617269"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

Gibt an, dass die digitale Signatur des Binärimages zur Ladezeit überprüft werden muss.

> **/ INTEGRITYCHECK**[**: NO**]

## <a name="remarks"></a>Hinweise

Mit dieser Option wird im Header der DLL-Datei oder der ausführbaren Datei ein Flag festgelegt, das eine Überprüfung der digitalen Signatur mithilfe des Speicher-Managers erfordert, um das Image in Windows zu laden. Windows-Versionen vor Windows Vista ignorieren dieses Flag. Diese Option muss für 64-Bit-DLLs festgelegt werden, die den Kernelmoduscode implementieren, und wird für alle Gerätetreiber empfohlen. Weitere Informationen finden Sie unter [Kernelmodus-Code: Signieren von Anforderungen an](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](../../build/reference/editbin-options.md)
