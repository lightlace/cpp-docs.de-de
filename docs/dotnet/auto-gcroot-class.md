---
title: Auto_gcroot-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b6afad3450aff2a9243b3e4a480a374fbcd14fc7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103865"
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