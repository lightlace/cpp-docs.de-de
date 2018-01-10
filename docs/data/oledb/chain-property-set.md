---
title: CHAIN_PROPERTY_SET | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CHAIN_PROPERTY_SET
dev_langs: C++
helpviewer_keywords: CHAIN_PROPERTY_SET macro
ms.assetid: 2bcf6d7d-f4e5-480d-9140-1e32a0994c94
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1de482b285f24ce9ed68bd70fa7b21b0b66a4d56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="chainpropertyset"></a>CHAIN_PROPERTY_SET
Dieses Makro Eigenschaftengruppen miteinander verkettet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
CHAIN_PROPERTY_SET(  
ChainClass   
)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 *ChainClass*  
 [in] Der Name der Klasse in der Ketteneigenschaften. Dies ist eine Klasse, generiert der ATL-Projekt-Assistent, der bereits eine Zuordnung (z. B. eine Sitzung oder den Befehl Objekt Quellklasse) enthält.  
  
## <a name="remarks"></a>Hinweise  
 Sie können einen Eigenschaftensatz von einer anderen Klasse, um eine eigene Klasse verkettet dann Zugriff auf die Eigenschaften direkt aus Ihrer Klasse.  
  
> [!CAUTION]
>  Verwenden Sie dieses Makro nur selten auf. Die falsche Verwendung kann dazu führen, dass einen Consumer die OLE DB-Konformitätstests fehlschlägt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)