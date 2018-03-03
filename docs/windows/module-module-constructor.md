---
title: 'Module:: Module-Konstruktor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Module
dev_langs:
- C++
helpviewer_keywords:
- Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24e74bf30f932fa8029c64d27ce55dd2a75a99aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="modulemodule-constructor"></a>Module::Module-Konstruktor
Initialisiert eine neue Instanz der Module-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
Module();  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieser Konstruktor ist geschützt und kann nicht aufgerufen werden, mit dem `new` Schlüsselwort. Rufen Sie stattdessen entweder [Module:: GetModule-Methode](../windows/module-getmodule-method.md) oder [Module:: Create-Methode](../windows/module-create-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)