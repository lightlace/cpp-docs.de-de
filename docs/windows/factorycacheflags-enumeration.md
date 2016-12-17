---
title: "FactoryCacheFlags-Enumeration"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::FactoryCacheFlags"
dev_langs: 
  - "C++"
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# FactoryCacheFlags-Enumeration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob die Factoryobjekte zwischengespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig wird die Factory Cachingrichtlinie als angegeben der [ModuleType](../windows/moduletype-enumeration.md) Vorlagenparameter bei der Erstellung ein [Modul](../windows/module-class.md) Objekt. Um diese Richtlinie zu überschreiben, geben Sie einen `FactoryCacheFlags` Wert, wenn Sie eine Factoryobjekt erstellen.  
  
|||  
|-|-|  
|`FactoryCacheDefault`|Die Cachingrichtlinie für die `Module` Objekt verwendet wird.|  
|`FactoryCacheEnabled`|Aktiviert das Factory zwischenspeichern, unabhängig von der `ModuleType` Vorlagenparameter, der verwendet wird, erstellen ein `Module` Objekt.|  
|`FactoryCacheDisabled`|Deaktiviert die Factory Zwischenspeichern unabhängig von der `ModuleType` Vorlagenparameter, der verwendet wird, erstellen ein `Module` Objekt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft:: wrl-Namespace](../windows/microsoft-wrl-namespace.md)