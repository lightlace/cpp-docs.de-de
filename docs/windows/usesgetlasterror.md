---
title: Usesgetlasterror | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 399b9fbbcf4b449f5f91beaea89c403d120d0a21
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="usesgetlasterror"></a>usesgetlasterror
Wird dem Aufrufer mitgeteilt, dass wenn ein Fehler aufgetreten ist, wenn diese Funktion aufgerufen wird, klicken Sie dann der Aufrufer aufrufen kann `GetLastError` auf den Fehlercode abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[usesgetlasterror]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **Usesgetlasterror** C++-Attribut hat die gleiche Funktionalität wie die [Usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter der [Idl_module](../windows/idl-module.md) Beispiel zur Verwendung **Usesgetlasterror**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Modul** Attribut|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
