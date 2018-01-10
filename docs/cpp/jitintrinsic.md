---
title: Jitintrinsic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 451f9e534284a2daa69ddc11495f6ecc8af1ee13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="jitintrinsic"></a>jitintrinsic
Markiert die Funktion als signifikant bei der 64-Bit-Common Language Runtime. Dies wird in bestimmten Funktionen in von Microsoft bereitgestellten Bibliotheken verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>Hinweise  
 `jitintrinsic` fügt ein MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) zu einer Funktionssignatur hinzu.  
  
 Benutzern wird von der Verwendung dieses `__declspec`-Modifizierers abgeraten, da unerwartete Ergebnisse auftreten können.  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)