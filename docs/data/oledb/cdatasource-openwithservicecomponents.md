---
title: 'CDataSource:: Openwithservicecomponents | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
dev_langs:
- C++
helpviewer_keywords:
- OpenWithServiceComponents method
ms.assetid: 49c1d037-36ae-4fde-8e54-ced623abe1a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0967888557d1a62952e0d1f0c23ee83b7d03550b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdatasourceopenwithservicecomponents"></a>CDataSource::OpenWithServiceComponents
Öffnet ein Datenquellenobjekt mithilfe der Dienstkomponenten in „oledb32.dll“.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  


HRESULT OpenWithServiceComponents (LPCSTR szProgID,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  
```  
  
#### <a name="parameters"></a>Parameter  
 `clsid`  
 [in] Die **CLSID** eines Datenanbieters.  
  
 `szProgID`  
 [in] Programm-ID eines Datenanbieters.  
  
 `pPropset`  
 [in] Ein Zeiger auf ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) Strukturen, die Eigenschaften und Werten festgelegt werden. Finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in der *OLE DB Programmer's Reference* im Windows SDK. Wenn das Datenquellenobjekt initialisiert wird, müssen die Eigenschaften zur Eigenschaftsquelle „Datenquelle“ gehören. Wenn dieselbe Eigenschaft mehrfach in `pPropset` angegeben wird, ist es anbieterspezifisch, welcher Wert verwendet wird. Wenn `ulPropSets` 0 ist, wird dieser Parameter ignoriert.  
  
 `ulPropSets`  
 [in] Die Anzahl der [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) Strukturen zu übergeben, der *DBPROPSET* Argument. Wenn dies 0 ist, ignoriert der Anbieter `pPropset`.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfunktionen wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw. Weitere Informationen finden Sie unter "OLE DB-Dienste" in der OLE DB Programmer's Reference am [http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataSource-Klasse](../../data/oledb/cdatasource-class.md)