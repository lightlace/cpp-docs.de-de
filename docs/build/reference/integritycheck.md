---
title: / INTEGRITYCHECK | Microsoft Docs
ms.custom: 
ms.date: 12/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99caec18162a7506b8b7a467eb7374b6fe4a38d9
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

Gibt an, dass die digitale Signatur des Binärimages zur Ladezeit überprüft werden muss.

> **/ INTEGRITYCHECK**[**: NO**]

## <a name="remarks"></a>Hinweise

Mit dieser Option wird im Header der DLL-Datei oder der ausführbaren Datei ein Flag festgelegt, das eine Überprüfung der digitalen Signatur mithilfe des Speicher-Managers erfordert, um das Image in Windows zu laden. Windows-Versionen vor Windows Vista ignorieren dieses Flag. Diese Option muss für 64-Bit-DLLs festgelegt werden, die den Kernelmoduscode implementieren, und wird für alle Gerätetreiber empfohlen. Weitere Informationen finden Sie unter [Kernelmodus-Code Signieren von Anforderungen](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](../../build/reference/editbin-options.md)  
