---
title: 'Handlet:: Close-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f0c1e47420106651cfe0526d6d212e9819a72ff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="handletclose-method"></a>HandleT::Close-Methode
Schließt das aktuelle HandleT-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
void Close();  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Handle, das den aktuellen HandleT zugrunde liegt wird geschlossen, und die HandleT auf einen ungültigen Zustand festgelegt ist.  
  
 Wenn das Handle nicht ordnungsgemäß geschlossen wird, wird in den aufrufenden Thread eine Ausnahme ausgelöst.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HandleT-Klasse](../windows/handlet-class.md)