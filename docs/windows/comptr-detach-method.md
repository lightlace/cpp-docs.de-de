---
title: 'Comptr:: Detach-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: b9016775-1ade-4581-be1f-0d6f9c2ca658
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abc30204969464323d4995310cee0866139734fc
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648008"
---
# <a name="comptrdetach-method"></a>ComPtr::Detach-Methode
Hebt die Zuordnung dieser **ComPtr** Objekt von der Schnittstelle, die es darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
T* Detach();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Schnittstelle, die von diesem dargestellt wurde **ComPtr** Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)