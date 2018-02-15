---
title: 'CXMLAccessor:: GetXMLColumnData | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
dev_langs:
- C++
helpviewer_keywords:
- GetXMLColumnData method
ms.assetid: 719e8efe-8758-4af7-a855-0e44ea196546
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0e9a11434be63b75eef5ac0aaed729b7a8c2f0b7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cxmlaccessorgetxmlcolumndata"></a>CXMLAccessor::GetXMLColumnData
Ruft die Typinformationen Spalte einer Tabelle als XML-formatierte Zeichenfolgedaten nach Spalten ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `strOutput`  
 [out] Ein Verweis auf einen Zeichenfolgenpuffer, enthält die Spalte Typinformationen abgerufen werden sollen. Die Zeichenfolge wird mit XML-Tagnamen formatiert, die den Datenspeicher Spaltennamen entsprechen.  
  
## <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Das folgende Beispiel zeigt, wie die Spalteninformationen für den Typ in XML formatiert ist. `type` Gibt an, der Datentyp der Spalte. Beachten Sie, dass die Datentypen auf OLE DB-Datentypen, die nicht die von der Datenbank, auf die zugegriffen wird basieren.  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CXMLAccessor-Klasse](../../data/oledb/cxmlaccessor-class.md)