---
title: ComPtr::Reset | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: aa6a46f7-f56b-4fd5-add0-7cea55f7abda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6edbe333ddb634d8657712695250ec627a171780
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461083"
---
# <a name="comptrreset"></a>ComPtr::Reset
Gibt alle Verweise für den Zeiger auf die Schnittstelle, die mit dieser verknüpft ist **ComPtr**.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned long Reset();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Die Anzahl der freigegeben Verweise, sofern vorhanden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)