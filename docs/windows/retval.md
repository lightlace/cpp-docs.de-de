---
title: Retval | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.retval
dev_langs:
- C++
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6f17f44e520018f82dc82abe88427a2410d68e7
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606350"
---
# <a name="retval"></a>retval
Legt fest, den Parameter, der den Rückgabewert des Members empfängt.  
  
## <a name="syntax"></a>Syntax  
  
```  
[retval]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **Retval** C++-Attribut hat die gleiche Funktionalität wie die [Retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL-Attribut.  
  
 **Retval** muss für das letzte Argument in einer Funktion Deklaration angezeigt werden.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [bindbare](../windows/bindable.md) für ein Beispiel für die Verwendung von **Retval**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Parameter, für die Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**out**|  
|**Ungültige Attribute**|**in**|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   