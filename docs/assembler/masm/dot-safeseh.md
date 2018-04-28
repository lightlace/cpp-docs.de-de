---
title: . SAFESEH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ea34448b4dae0525e7feb2fd7cca310a95a6e3c
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="safeseh"></a>.SAFESEH
Registriert eine Funktion als strukturierte Ausnahmehandler.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
.SAFESEH identifier  
```  
  
## <a name="remarks"></a>Hinweise  
 *Bezeichner* muss die ID für eine lokal definierte [PROC](../../assembler/masm/proc.md) oder [EXTRN](../../assembler/masm/extrn.md) PROC. Ein [Bezeichnung](../../assembler/masm/label-masm.md) ist nicht zulässig. Die. SAFESEH-Anweisung erfordert die [/SAFESEH](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe-Befehlszeilenoption.  
  
 Weitere Informationen zu strukturierten Ausnahmehandler, finden Sie unter [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).  
  
 Beispielsweise um eine sichere Ausnahmehandler registrieren, erstellen Sie eine neue MASM-Datei (wie folgt), mit/SAFESEH zusammenzustellen Sie und verknüpfte Objekte hinzuzufügen.  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)