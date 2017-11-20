---
title: . SAFESEH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .SAFESEH
dev_langs: C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bcbcafef4ad548ab784740a4130fc1679bf43f0a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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