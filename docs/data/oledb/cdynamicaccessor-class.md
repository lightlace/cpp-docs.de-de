---
title: CDynamicAccessor-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicAccessor class
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2a4006afa9ebdfcf95a01103d1fd97643a6b749f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098302"
---
# <a name="cdynamicaccessor-class"></a>CDynamicAccessor-Klasse
Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse des Datenbankschemas (die zugrunde liegende Struktur) verfügen.  
  
## <a name="syntax"></a>Syntax

```cpp
class CDynamicAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cdynamicaccessor-addbindentry.md)|Fügt eine Bindung den Ausgabespalten zum Überschreiben den Standardeinstellung-Accessor.|  
|[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)|Instanziiert und initialisiert die `CDynamicAccessor` Objekt.|  
|[Schließen](../../data/oledb/cdynamicaccessor-close.md)|Hebt die Bindung auf alle Spalten, die den zugeordneten Arbeitsspeicher frei und gibt die [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) Schnittstellenzeiger in der Klasse.|  
|[GetBookmark](../../data/oledb/cdynamicaccessor-getbookmark.md)|Ruft das Lesezeichen für die aktuelle Zeile ab.|  
|[GetBlobHandling](../../data/oledb/cdynamicaccessor-getblobhandling.md)|Ruft das BLOB Behandlung von Wert für die aktuelle Zeile ab.|  
|[GetBlobSizeLimit](../../data/oledb/cdynamicaccessor-getblobsizelimit.md)|Ruft die maximale BLOB-Größe in Bytes ab.|  
|[GetColumnCount](../../data/oledb/cdynamicaccessor-getcolumncount.md)|Ruft die Anzahl der Spalten im Rowset ab.|  
|[GetColumnFlags](../../data/oledb/cdynamicaccessor-getcolumnflags.md)|Ruft die Spalteneigenschaften ab.|  
|[GetColumnInfo](../../data/oledb/cdynamicaccessor-getcolumninfo.md)|Ruft die Metadaten ab.|  
|[GetColumnName](../../data/oledb/cdynamicaccessor-getcolumnname.md)|Ruft den Namen einer angegebenen Spalte ab.|  
|[GetColumnType](../../data/oledb/cdynamicaccessor-getcolumntype.md)|Ruft den Datentyp einer angegebenen Spalte ab.|  
|[getLength](../../data/oledb/cdynamicaccessor-getlength.md)|Ruft die maximal mögliche Länge einer Spalte in Bytes ab.|  
|[GetOrdinal](../../data/oledb/cdynamicaccessor-getordinal.md)|Ruft den Spaltenindex erhält einen Spaltennamen ab.|  
|[GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)|Ruft den Status einer angegebenen Spalte ab.|  
|[GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)|Ruft die Daten aus dem Puffer ab.|  
|[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)|Legt das BLOB Behandlung von Wert für die aktuelle Zeile fest.|  
|[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)|Legt die maximale BLOB-Größe in Bytes fest.|  
|[SetLength](../../data/oledb/cdynamicaccessor-setlength.md)|Legt die Länge der Spalte in Bytes fest.|  
|[SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)|Setzt den Status einer angegebenen Spalte.|  
|[SetValue](../../data/oledb/cdynamicaccessor-setvalue.md)|Speichert die Daten in den Puffer.|  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `CDynamicAccessor` Methoden zum Abrufen von Informationen in der Spalte z. B. Spaltennamen, Spaltenanzahl, Datentyp und So weiter. Klicken Sie dann verwenden Sie diese Informationen in der Spalte um einen Accessor zur Laufzeit dynamisch zu erstellen.  
  
 Die Informationen in der Spalte wird in einem Puffer gespeichert, die erstellt und verwaltet wird von dieser Klasse. Abrufen von Daten aus dem Puffer mithilfe [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).  
  
 Ausführliche Informationen und Beispiele für die Verwendung der dynamischen Accessors-Klassen finden Sie unter [mithilfe von dynamischen Accessoren](../../data/oledb/using-dynamic-accessors.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumer-Vorlagenreferenz](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)