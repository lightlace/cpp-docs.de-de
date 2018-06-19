---
title: 'CRowset:: UpdateAll | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset::UpdateAll
- ATL.CRowset.UpdateAll
- CRowset<TAccessor>.UpdateAll
- ATL.CRowset<TAccessor>.UpdateAll
- UpdateAll
- CRowset.UpdateAll
- ATL::CRowset<TAccessor>::UpdateAll
- CRowset<TAccessor>::UpdateAll
- ATL::CRowset::UpdateAll
dev_langs:
- C++
helpviewer_keywords:
- UpdateAll method
ms.assetid: e5b26c0a-40fc-4c91-a293-5084951788e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d9e21cd34a4d758becb12b529fe858e96d18f187
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092190"
---
# <a name="crowsetupdateall"></a>CRowset::UpdateAll
Überträgt alle ausstehenden Änderungen, die seit dem letzten Abruf auf alle Zeilen oder **Update** dafür aufrufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT UpdateAll(DBCOUNTITEM* pcRows = NULL,   
   HROW** pphRow = NULL,   
   DBROWSTATUS** ppStatus = NULL) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `pcRows`  
 [out] Ein Zeiger auf den Speicherort, in dem `UpdateAll` gibt die Anzahl der Zeilen zu aktualisieren, versucht, falls erforderlich.  
  
 `pphRow`  
 [out] Ein Zeiger auf Speicher, in den `UpdateAll` gibt das Handle der Zeile, die es versucht, zu aktualisieren. Kein Handle wird zurückgegeben, wenn `pphRow` ist null.  
  
 `ppStatus`  
 [out] Ein Zeiger auf den Speicherort, in dem **Update** den Statuswert Zeile zurückgibt. Es wird kein Status zurückgegeben, wenn `ppStatus` ist null.  
  
## <a name="remarks"></a>Hinweise  
 Überträgt alle Änderungen an allen Zeilen vorgenommen werden, da die Zeilen zuletzt abgerufen wurden oder mithilfe aktualisieren [Update](../../data/oledb/crowset-update.md) oder `UpdateAll`. `UpdateAll` Jede Zeile, die geändert wurde unabhängig davon, ob Sie weiterhin das Handle für diese verfügen, werden aktualisiert (finden Sie unter `pphRow`) oder nicht.  
  
 Angenommen, Sie verwendet **einfügen** um fünf Zeilen in einem Rowset einzufügen, können Sie entweder Aufruf **aktualisieren** fünfmal oder Aufruf `UpdateAll` einmal, um alle aktualisieren.  
  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetUpdate`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetUpdate** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)