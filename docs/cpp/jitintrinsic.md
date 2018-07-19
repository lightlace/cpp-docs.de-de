---
title: Jitintrinsic | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f8b1c932f53651b8ad116139724348714b183506
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939389"
---
# <a name="jitintrinsic"></a>jitintrinsic
Markiert die Funktion als signifikant bei der 64-Bit-Common Language Runtime. Dies wird in bestimmten Funktionen in von Microsoft bereitgestellten Bibliotheken verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>Hinweise  
 `jitintrinsic` fügt ein MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) zu einer Funktionssignatur hinzu.  
  
 Benutzer sind nicht empfehlenswert, von der Verwendung dieses **__declspec** Modifizierer verwenden, da unerwartete Ergebnisse möglich.  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)