---
title: 'CXMLAccessor:: GetXMLColumnData | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ad3921a25e01f3269fe50f37fbc227a60e12cb43
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100654"
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