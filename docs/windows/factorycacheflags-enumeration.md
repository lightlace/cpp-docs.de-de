---
title: FactoryCacheFlags-Enumeration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
dev_langs:
- C++
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc4bd998368fb325878a81ee4954a2ceec9432fe
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570102"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags-Enumeration
Bestimmt, ob die Factory-Objekte zwischengespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>Hinweise  
 In der Standardeinstellung die Cacherichtlinie Factory angegeben ist, als die [ModuleType](../windows/moduletype-enumeration.md) Template-Parameter, die bei der Erstellung einer [Modul](../windows/module-class.md) Objekt. Um diese Richtlinie überschreiben, geben Sie einen **FactoryCacheFlags** Wert, wenn Sie ein Factoryobjekt zu erstellen.  
  
|||  
|-|-|  
|`FactoryCacheDefault`|Die Cachingrichtlinie für die `Module` Objekt verwendet wird.|  
|`FactoryCacheEnabled`|Aktiviert die Factory Zwischenspeicherung, unabhängig von der `ModuleType` Vorlagenparameter, der zum Erstellen einer `Module` Objekt.|  
|`FactoryCacheDisabled`|Deaktiviert die Factory im Cache unabhängig von der `ModuleType` Vorlagenparameter, der zum Erstellen einer `Module` Objekt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)