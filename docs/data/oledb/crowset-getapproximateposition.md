---
title: 'CRowset:: Getapproximateposition | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRowset::GetApproximatePosition
- ATL::CRowset<TAccessor>::GetApproximatePosition
- CRowset.GetApproximatePosition
- CRowset::GetApproximatePosition
- GetApproximatePosition
- ATL.CRowset.GetApproximatePosition
- CRowset<TAccessor>::GetApproximatePosition
dev_langs: C++
helpviewer_keywords: GetApproximatePosition method
ms.assetid: 8f9ccd41-0590-468e-b202-6731d0f99d21
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 86d6e17c3bfe01cc579e9a0afab8f555419e5116
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetgetapproximateposition"></a>CRowset::GetApproximatePosition
Gibt die ungefähre Position einer Zeile zu einem Lesezeichen entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT GetApproximatePosition(   
   const CBookmarkBase* pBookmark,   
   DBCOUNTITEM* pPosition,   
   DBCOUNTITEM* pcRows    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pBookmark`  
 [in] Ein Zeiger auf ein Lesezeichen, das die Zeile identifiziert, dessen Position gesucht wird. **NULL** nur die Anzahl der Zeilen erforderlich ist.  
  
 *pPosition*  
 [out] Ein Zeiger auf den Speicherort, in dem `GetApproximatePosition` gibt die Position der Zeile zurück. **NULL** , wenn die Position nicht erforderlich ist.  
  
 `pcRows`  
 [out] Ein Zeiger auf den Speicherort, in dem `GetApproximatePosition` gibt die Gesamtzahl der Zeilen zurück. **NULL** , wenn die Anzahl der Zeilen nicht erforderlich ist.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetScroll`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetScroll** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
 Informationen zur Verwendung von Lesezeichen in Consumer finden Sie unter [mithilfe von Lesezeichen](../../data/oledb/using-bookmarks.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetScroll::GetApproximatePosition](https://msdn.microsoft.com/en-us/library/ms712901.aspx)