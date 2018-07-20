---
title: 'Roinitializewrapper:: Roinitializewrapper-Konstruktor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64f2af40c671760bb8d4e667c209598c46b24665
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889204"
---
# <a name="roinitializewrapperroinitializewrapper-constructor"></a>RoInitializeWrapper::RoInitializeWrapper-Konstruktor
Initialisiert eine neue Instanz der RoInitializeWrapper-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
RoInitializeWrapper(   RO_INIT_TYPE flags)  
```  
  
#### <a name="parameters"></a>Parameter  
 `flags`  
 Einer der RO_INIT_TYPE Enumerationen, die zur Unterstützung von Windows-Runtime angibt.  
  
## <a name="remarks"></a>Hinweise  
 RoInitializeWrapper-Klasse ruft Windows::Foundation::Initialize (*Flags*).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HandleT-Klasse](../windows/handlet-class.md)