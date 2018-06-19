---
title: XMMWORD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- XMMWORD
dev_langs:
- C++
helpviewer_keywords:
- XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8fd8e6c82a3275161e519eeead490473e8d64ab
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32056417"
---
# <a name="xmmword"></a>XMMWORD
Für 128-Bit-multimedia-Operanden mit MMX- und SSE (XMM)-Anweisungen verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
XMMWORD  
```  
  
## <a name="remarks"></a>Hinweise  
 `XMMWORD` Dient zur Darstellung der vom selben Typs wie [__m128](../../cpp/m128.md).  
  
## <a name="example"></a>Beispiel  
  
```  
movdqa   xmm0, xmmword ptr [ebx]  
```