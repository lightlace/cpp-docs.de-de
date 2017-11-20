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
ms.openlocfilehash: 04cdfc3d40bcf45db45998700a9a0a5d1c1177d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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