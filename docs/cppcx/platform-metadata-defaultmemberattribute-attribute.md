---
title: Platform::Metadata::DefaultMemberAttribute-Attribut | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::DefaultMemberAttribute
dev_langs:
- C++
helpviewer_keywords:
- Platform::Metadata::DefaultMemberAttribute Attribute
ms.assetid: d8abda01-c257-4371-aec4-541d4825e0af
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2233dd96f483df632c7ff8cd5b1a7a051232c94d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33087935"
---
# <a name="platformmetadatadefaultmemberattribute-attribute"></a>Platform::Metadata::DefaultMemberAttribute-Attribut
Gibt die bevorzugte Funktion an, um unter mehreren möglichen überladenen Funktionen aufzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
  
public ref class DefaultMember abstract : Attribute  
```  
  
## <a name="inheritance"></a>Vererbung  
 [Platform::Object](../cppcx/platform-object-class.md)   
  
 [Platform::Metadata::Attribute](../cppcx/platform-metadata-attribute-attribute.md)  
  
### <a name="remarks"></a>Hinweise  
 Wenden Sie das DefaultMember-Attribut auf eine Methode an, die von einer JavaScript-Anwendung verwendet wird.  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform::Metadata  
  
 **Metadaten:** platform.winmd  
  
## <a name="see-also"></a>Siehe auch  
 [Platform::Metadata-Namespace](../cppcx/platform-metadata-namespace.md)