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
ms.openlocfilehash: 69f3f2c756d158954676f6fc42941b1b80f4345e
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569917"
---
# <a name="handletclose-method"></a>HandleT::Close-Methode
Schließt das aktuelle **HandleT** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
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