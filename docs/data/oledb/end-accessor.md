---
title: END_ACCESSOR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: END_ACCESSOR
dev_langs: C++
helpviewer_keywords: END_ACCESSOR macro
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f0dceb1fe648a67d10fb18b353a5de54fa39caee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="endaccessor"></a>END_ACCESSOR
Markiert das Ende eines Eintrags Accessor.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
END_ACCESSOR( )  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Für mehrere Accessoren für ein Rowset, müssen Sie angeben `BEGIN_ACCESSOR_MAP` und Verwenden der `BEGIN_ACCESSOR` -Makro für jede einzelne Zugriffsmethode. Das `BEGIN_ACCESSOR` -Makro wird mit dem `END_ACCESSOR` -Makro abgeschlossen. Die `BEGIN_ACCESSOR_MAP` Makro erfolgt mit der `END_ACCESSOR_MAP` Makro.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)