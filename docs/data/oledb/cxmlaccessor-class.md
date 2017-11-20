---
title: CXMLAccessor-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
dev_langs: C++
helpviewer_keywords: CXMLAccessor class
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 102dee928d1a6b8bbfcde80c46f097d67cf76a42
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor-Klasse
Gibt Ihnen Zugriff auf Datenquellen als Zeichenfolgendaten, wenn Sie keine Kenntnisse der Datenspeicher-Schema (zugrunde liegende Struktur) verfügen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)|Ruft die Informationen in der Spalte ab.|  
|[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)|Ruft den gesamten Inhalt einer Tabelle nach Zeilen ab.|  
  
## <a name="remarks"></a>Hinweise  
 Allerdings `CXMLAccessor` unterscheidet sich von `CDynamicStringAccessorW` , konvertiert Sie alle Daten aus dem Datenspeicher als XML-Format (tagged) Daten zugegriffen. Dies ist besonders nützlich für die Ausgabe auf XML-fähigen Webseiten. Die XML-Tagnamen entspricht der Datenspeicher Spaltennamen so getreu wie möglich.  
  
 Verwendung `CDynamicAccessor` Methoden zum Abrufen von Spalteninformationen. Sie verwenden diese Informationen in der Spalte um einen Accessor zur Laufzeit dynamisch zu erstellen.  
  
 Die Informationen in der Spalte befindet sich in einem Puffer, die von dieser Klasse erstellt und verwaltet. Rufen Sie Spalte Informationen mit [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) oder Spaltendaten abrufen, indem Sie Zeilen mithilfe von [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumer-Vorlagenreferenz](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA-Klasse](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW-Klasse](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)