---
title: 'Module:: Module-Konstruktor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Module
dev_langs:
- C++
helpviewer_keywords:
- Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b31e9f1e4536bc124bba359ece10217ef8b7f253
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875252"
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