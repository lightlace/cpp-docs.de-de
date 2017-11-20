---
title: 'CDynamicAccessor:: GetBookmark | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
dev_langs: C++
helpviewer_keywords: GetBookmark method
ms.assetid: 6d0a2970-0c62-4a34-bac7-149d8e990f81
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d9c8f6a2567684ffb7c7faee62cdca501c53ba0c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorgetbookmark"></a>CDynamicAccessor::GetBookmark
Ruft das Lesezeichen für die aktuelle Zeile ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT GetBookmark(   
   CBookmark< >* pBookmark    
) const throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pBookmark`  
 [out] Ein Zeiger auf die [CBookmark](../../data/oledb/cbookmark-class.md) Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen festlegen **DBPROP_IRowsetLocate** auf `VARIANT_TRUE` ein Lesezeichens abgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)