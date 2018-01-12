---
title: 'CRowset:: Update | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset.Update
- ATL.CRowset.Update
- ATL.CRowset<TAccessor>.Update
- ATL::CRowset<TAccessor>::Update
- CRowset<TAccessor>::Update
- CRowset::Update
- CRowset<TAccessor>.Update
- ATL::CRowset::Update
dev_langs: C++
helpviewer_keywords: Update method
ms.assetid: cd5fedc8-2b85-4cb8-8c40-c79576316903
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 26cbada107bbefe4c5e32243f2761193b1912a0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetupdate"></a>CRowset::Update
Überträgt alle ausstehenden Änderungen an der aktuellen Zeile seit der letzten Fetch oder **Update** dafür aufrufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT Update(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pcRows`  
 [out] Ein Zeiger auf den Speicherort, in dem **aktualisieren** gibt die Anzahl der Zeilen zu aktualisieren, versucht, falls erforderlich.  
  
 `phRow`  
 [out] Ein Zeiger auf den Speicherort, in dem **aktualisieren** gibt das Handle der Zeile, die es versucht, zu aktualisieren. Kein Handle wird zurückgegeben, wenn `phRow` ist null.  
  
 `pStatus`  
 [out] Ein Zeiger auf den Speicherort, in dem **Update** den Statuswert Zeile zurückgibt. Es wird kein Status zurückgegeben, wenn `pStatus` ist null.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Überträgt alle Änderungen an der aktuellen Zeile vorgenommen werden, da diese Zeile zuletzt abgerufen oder aktualisiert wurde (mit **Update** oder [UpdateAll](../../data/oledb/crowset-updateall.md)). Rufen Sie in der Regel [SetData](../../data/oledb/crowset-setdata.md) von Datenwerten in Spalten in einer Zeile festgelegt, und rufen Sie anschließend **Update** diese Änderungen zu übertragen.  
  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetUpdate`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetUpdate** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate:: Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset:: UpdateAll](../../data/oledb/crowset-updateall.md)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)