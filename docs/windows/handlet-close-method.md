---
title: 'Handlet:: Close-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: 7cbe76cdea5c8fadef818ede1d63d88e4437bdae
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651066"
---
# <a name="handletclose-method"></a>HandleT::Close-Methode
Schließt das aktuelle **HandleT** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void Close();  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Handle, das das aktuelle zugrunde liegende **HandleT** wird geschlossen, und die **HandleT** auf einen ungültigen Zustand festgelegt ist.  
  
 Wenn das Handle nicht ordnungsgemäß geschlossen wird, wird eine Ausnahme im aufrufenden Thread ausgelöst.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HandleT-Klasse](../windows/handlet-class.md)