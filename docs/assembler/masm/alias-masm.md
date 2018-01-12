---
title: ALIAS (MASM) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Alias
dev_langs: C++
helpviewer_keywords: ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59dc4fd5481b22e69153c68e94a81b2887118ebc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="alias-masm"></a>ALIAS (MASM)
Die **ALIAS** Richtlinie erstellt, einen alternativen Name für eine Funktion.  Dadurch können Sie mehrere Namen für eine Funktion erstellen, oder erstellen Sie Bibliotheken, mit die den Linker (LINK.exe) eine alte Funktion in eine neue Funktion zuordnen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
ALIAS  <  
alias  
> = <  
actual-name  
>  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `actual-name`  
 Der tatsächliche Name der Funktion oder Prozedur.  Die spitzen Klammern sind erforderlich.  
  
 `alias`  
 Der Name des alternativen oder Alias.  Die spitzen Klammern sind erforderlich.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)