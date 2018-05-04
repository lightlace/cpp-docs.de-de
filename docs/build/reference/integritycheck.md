---
title: / INTEGRITYCHECK | Microsoft Docs
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /INTEGRITYCHECK
dev_langs:
- C++
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b0adf9add2d191ae89aec0a5d756ade8e9f7725
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

Gibt an, dass die digitale Signatur des Binärimages zur Ladezeit überprüft werden muss.

> **/ INTEGRITYCHECK**[**: NO**]

## <a name="remarks"></a>Hinweise

Mit dieser Option wird im Header der DLL-Datei oder der ausführbaren Datei ein Flag festgelegt, das eine Überprüfung der digitalen Signatur mithilfe des Speicher-Managers erfordert, um das Image in Windows zu laden. Windows-Versionen vor Windows Vista ignorieren dieses Flag. Diese Option muss für 64-Bit-DLLs festgelegt werden, die den Kernelmoduscode implementieren, und wird für alle Gerätetreiber empfohlen. Weitere Informationen finden Sie unter [Kernelmodus-Code Signieren von Anforderungen](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](../../build/reference/editbin-options.md)  
