---
title: ALIAS (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Alias
dev_langs:
- C++
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b14e1c41a448d0cb7014dabc50a42305249938f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049166"
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