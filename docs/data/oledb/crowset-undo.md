---
title: 'CRowset:: Undo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset.Undo
- ATL::CRowset<TAccessor>::Undo
- CRowset<TAccessor>::Undo
- ATL.CRowset.Undo
- ATL.CRowset<TAccessor>.Undo
- CRowset<TAccessor>.Undo
- ATL::CRowset::Undo
- CRowset::Undo
- Undo
dev_langs: C++
helpviewer_keywords: Undo method
ms.assetid: 1ccd70e2-3931-41c4-893e-a05d0e295410
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 33213cb9780846639de6638bc3028a3e656d1a9e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetundo"></a>CRowset::Undo
Macht alle Änderungen an einer Zeile seit der letzten Fetch oder [Update](../../data/oledb/crowset-update.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT Undo(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pcRows`  
 [out] Ein Zeiger auf den Speicherort, in dem **Rückgängig** gibt die Anzahl der Zeilen, die versucht wurde, rückgängig machen, wenn erforderlich.  
  
 `phRow`  
 [out] Ein Zeiger auf den Speicherort, in dem **Rückgängig** gibt ein Array von Handles, alle Zeilen, die versucht wurde, rückgängig machen, wenn erforderlich.  
  
 `pStatus`  
 [out] Ein Zeiger auf den Speicherort, in dem **Rückgängig** den Statuswert Zeile zurückgibt. Es wird kein Status zurückgegeben, wenn `pStatus` ist null.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetUpdate`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetUpdate** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)