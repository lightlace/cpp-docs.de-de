---
title: Auto_gcroot-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bb203193d1568056c631d90a2e1f5b1cf1d00e5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="autogcroot-class"></a>auto_gcroot-Klasse
Automatische ressourcenverwaltung (z. B. [Auto_ptr-Klasse](../standard-library/auto-ptr-class.md)) die zum Einbetten von eines virtuellen Handles in einen systemeigenen Typ verwendet werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename _element_type>  
class auto_gcroot;  
```  
  
#### <a name="parameters"></a>Parameter  
 `_element_type`  
 Der verwaltete Typ, eingebettet werden soll.  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<msclr\auto_gcroot.h >  
  
 **Namespace** Msclr  
  
## <a name="see-also"></a>Siehe auch  
 [auto_gcroot](../dotnet/auto-gcroot.md)   
 [Auto_gcroot-Elemente](../dotnet/auto-gcroot-members.md)   
 [Vorgehensweise: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md)   
 [auto_handle-Klasse](../dotnet/auto-handle-class.md)