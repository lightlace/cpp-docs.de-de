---
title: 'IRowsetImpl:: GetDBStatus | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
dev_langs: C++
helpviewer_keywords: GetDBStatus method
ms.assetid: e51d8ee2-fc0c-4909-861c-026c94fb0dfc
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bcfa368eaac89c1b7f0a094c139fc2434691e143
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplgetdbstatus"></a>IRowsetImpl::GetDBStatus
Gibt die `DBSTATUS` Statusflags für das angegebene Feld.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      virtual DBSTATUS GetDBStatus(  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `currentRow`  
 Die aktuelle Zeile.  
  
 [in] `columnNames`  
 Die Spalte, deren Status angefordert wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Die [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) Flags für die Spalte.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)