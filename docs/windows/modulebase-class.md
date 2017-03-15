---
title: "ModuleBase-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::ModuleBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ModuleBase-Klasse"
ms.assetid: edce7591-6893-46f7-94a7-382827775548
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ModuleBase-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL-Infrastruktur und ist nicht direkt aus dem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class ModuleBase;  
```  
  
## <a name="remarks"></a>Hinweise  
 Stellt die Basisklasse für die [Modul](../windows/module-class.md) Klassen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Modulebase:: Modulebase-Konstruktor](../windows/modulebase-modulebase-constructor.md)|Initialisiert eine Instanz der Modul-Klasse.|  
|[ModuleBase:: ~ ModuleBase-Destruktor](../windows/modulebase-tilde-modulebase-destructor.md)|Hebt die Initialisierung der aktuellen Instanz der Modul-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Modulebase:: Decrementobjectcount-Methode](../windows/modulebase-decrementobjectcount-method.md)|Bei der Implementierung nachverfolgt verringert die Anzahl der Objekte vom Modul an.|  
|[Modulebase:: Incrementobjectcount-Methode](../windows/modulebase-incrementobjectcount-method.md)|Bei der Implementierung erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ModuleBase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)