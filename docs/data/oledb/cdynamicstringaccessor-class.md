---
title: CDynamicStringAccessor-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicStringAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessor class
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 72ca3d1626b22f286a7e1ca9a276582d68cd7619
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicstringaccessor-class"></a>CDynamicStringAccessor-Klasse
Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse des Datenbankschemas (die zugrunde liegende Struktur) verfügen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)|Ruft die Daten der angegebenen Spalte als eine Zeichenfolge ab.|  
|[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)|Legt die angegebene Spalte als eine Zeichenfolge fest.|  
  
## <a name="remarks"></a>Hinweise  
 Während [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) fordert Daten im systemeigenen Format, die vom Anbieter gemeldeten `CDynamicStringAccessor` fordert an, dass der Anbieter alle Daten, die aus dem Datenspeicher als Zeichenfolgedaten zugegriffen abzurufen. Dies ist besonders für einfache Aufgaben, die keine Berechnung von Werten im Datenspeicher, z. B. anzeigen oder Drucken der Datenspeicher Inhalt erforderlich ist.  
  
 Der systemeigene Typ der Spaltendaten in den Datenspeicher spielt keine Rolle. solange der Anbieter die Datenkonvertierung unterstützen kann, werden die Daten im Zeichenfolgenformat bereitgestellt werden. Wenn der Anbieter die Konvertierung von systemeigenen Datentyp in eine Zeichenfolge nicht unterstützt (die nicht üblich ist), der anfordernde Aufruf zurück, der Erfolgswert **DB_S_ERRORSOCCURED**, und der Status für die entsprechende Spalte werden sollen. ein betreffendes Konvertierung **DBSTATUS_E_CANTCONVERTVALUE**.  
  
 Verwendung `CDynamicStringAccessor` Methoden zum Abrufen von Spalteninformationen. Sie verwenden diese Informationen in der Spalte um einen Accessor zur Laufzeit dynamisch zu erstellen.  
  
 Die Informationen in der Spalte befindet sich in einem Puffer, die von dieser Klasse erstellt und verwaltet. Abrufen von Daten aus dem Puffer mithilfe [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md), oder speichern Sie sie in den Puffer mit [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
 Ausführliche Informationen und Beispiele für die Verwendung der dynamischen Accessors-Klassen finden Sie unter [mithilfe von dynamischen Accessoren](../../data/oledb/using-dynamic-accessors.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumer-Vorlagenreferenz](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessorA-Klasse](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW-Klasse](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CXMLAccessor-Klasse](../../data/oledb/cxmlaccessor-class.md)