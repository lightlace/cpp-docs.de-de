---
title: FactoryCacheFlags-Enumeration | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::FactoryCacheFlags
dev_langs: C++
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb4efeb716255ae67a01fca7cf04a54816e227d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags-Enumeration
Bestimmt, ob die Factory-Objekte zwischengespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig die Factory Cachingrichtlinie angegeben ist, als die [ModuleType](../windows/moduletype-enumeration.md) Vorlagenparameter bei der Erstellung einer [Modul](../windows/module-class.md) Objekt. Um diese Richtlinie zu überschreiben, geben Sie einen `FactoryCacheFlags` Wert, wenn Sie ein Factoryobjekt erstellen.  
  
|||  
|-|-|  
|`FactoryCacheDefault`|Die Cachingrichtlinie für die `Module` Objekt verwendet wird.|  
|`FactoryCacheEnabled`|Ermöglicht das Factory zwischenspeichern, unabhängig von der `ModuleType` Vorlagenparameter, der zum Erstellen einer `Module` Objekt.|  
|`FactoryCacheDisabled`|Deaktiviert das Zwischenspeichern der Factory unabhängig von der `ModuleType` Vorlagenparameter, der zum Erstellen einer `Module` Objekt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)