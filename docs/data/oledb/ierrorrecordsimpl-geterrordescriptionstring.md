---
title: 'IErrorRecordsImpl:: Geterrordescriptionstring | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
dev_langs:
- C++
helpviewer_keywords:
- GetErrorDescriptionString method
ms.assetid: 8bc71c45-ca9f-4632-bb02-1aa9ed8086c4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b52bfba3313b6d5fe6423f3911bbef6af5253e86
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ierrorrecordsimplgeterrordescriptionstring"></a>IErrorRecordsImpl::GetErrorDescriptionString
Ruft die Zeichenfolge zur fehlerbeschreibung aus Error-Datensatzes ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      LPOLESTR GetErrorDescriptionString(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parameter  
 `rCurError`  
 Ein `ERRORINFO` Datensatz in einer **IErrorInfo** Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Zeichenfolge, die den Fehler beschreibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IErrorRecordsImpl-Klasse](../../data/oledb/ierrorrecordsimpl-class.md)