---
title: 'CRowsetImpl:: Namefromdbid | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
dev_langs: C++
helpviewer_keywords: NameFromDBID method
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: afe16dfefa719760c998c25cc107ba99caacff84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetimplnamefromdbid"></a>CRowsetImpl::NameFromDBID
Extrahiert eine Zeichenfolge aus einem **DBID** und kopiert ihn auf die `bstr` übergeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT CRowsetBaseImpl::NameFromDBID(  
   DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pDBID*  
 [in] Ein Zeiger auf die **DBID** aus der Zeichenfolge extrahiert.  
  
 `bstr`  
 [in] Ein [CComBSTR](../../atl/reference/ccombstr-class.md) Verweis platziert eine Kopie der **DBID** Zeichenfolge.  
  
 `bIndex`  
 [in] **"true"** Wenn ein Index **DBID**; **"false"** Wenn eine Tabelle **DBID**.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt. Je nachdem, ob die **DBID** ist eine Tabelle oder eines Indexes (gekennzeichnet durch `bIndex`), die Methode wird entweder **DB_E_NOINDEX** oder **DB_E_NOTABLE**.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem Sie die `CRowsetImpl` Implementierungen von [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) und [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CRowsetImpl-Klasse](../../data/oledb/crowsetimpl-class.md)