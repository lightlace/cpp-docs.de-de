---
title: AUFRUFEN | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Invoke
dev_langs:
- C++
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27c18c83b623ce1a22ffcb5e1a9f1ce98ee6eb20
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055169"
---
# <a name="invoke"></a>INVOKE
Die Prozedur aufruft, bei der Adresse, die vom *Ausdruck*, wobei die Argumente übergeben werden, auf dem Stapel oder in Registern gemäß dem standard Aufrufkonventionen des Typs Language.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
INVOKE   
expression [[, arguments]]  
```  
  
## <a name="remarks"></a>Hinweise  
 Jedes Argument an die Prozedur übergebenen möglicherweise einen Ausdruck, ein Registerpaar oder einen Adressausdruck (ein Ausdruck vorangestellt `ADDR`).  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)