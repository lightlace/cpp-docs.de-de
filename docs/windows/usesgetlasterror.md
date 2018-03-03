---
title: Usesgetlasterror | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05c74f1254230270654b3dc0b44f541e4fe9ef2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
