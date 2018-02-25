---
title: CDynamicParameterAccessor-Klasse | Microsoft Docs
ms.custom: 
ms.date: 02/14/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicParameterAccessor class
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18f53ca6d95d215ad41c6b2501245be0e470bbb1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor-Klasse

Ähnlich wie [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) Parameter Plattforminformationen durch Aufrufen von festgelegt werden, aber die [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-cdynamicparameteraccessor.md)|Der Konstruktor.|
|[GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md)|Ruft die Parameterdaten aus dem Puffer ab.|
|[GetParamCount](../../data/oledb/cdynamicparameteraccessor-getparamcount.md)|Ruft die Anzahl von Parametern im Accessor ab.|
|[GetParamIO](../../data/oledb/cdynamicparameteraccessor-getparamio.md)|Ermittelt, ob der angegebene Parameter ein Eingabe- oder ein Ausgabeparameter ist.|
|[GetParamLength](../../data/oledb/cdynamicparameteraccessor-getparamlength.md)|Ruft die Länge des angegebenen Parameters ab, der im Puffer gespeichert ist.|
|[GetParamName](../../data/oledb/cdynamicparameteraccessor-getparamname.md)|Ruft den Namen eines angegebenen Parameters ab.|
|[GetParamStatus](../../data/oledb/cdynamicparameteraccessor-getparamstatus.md)|Ruft den Status des angegebenen Parameters ab, der im Puffer gespeichert ist.|
|[GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)|Ruft die Zeichenfolgendaten Status des angegebenen Parameters ab, der im Puffer gespeichert ist.|
|[GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)|Ruft den Datentyp eines angegebenen Parameters ab.|
|[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)|Verwendet die Parameterdaten, um den Puffer festzulegen.|
|[SetParamLength](../../data/oledb/cdynamicparameteraccessor-setparamlength.md)|Legt die Länge des angegebenen Parameters fest, der im Puffer gespeichert ist.|
|[SetParamStatus](../../data/oledb/cdynamicparameteraccessor-setparamstatus.md)|Legt den Status des angegebenen Parameters fest, der im Puffer gespeichert ist.|
|[SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)|Legt die Zeichenfolgendaten des angegebenen Parameters fest, der im Puffer gespeichert ist.|

## <a name="remarks"></a>Hinweise

Der Anbieter muss `ICommandWithParameters` unterstützen, damit der Consumer diese Klasse verwenden kann.

Die Parameterinformationen werden in einem Puffer gespeichert, der von dieser Klasse erstellt und verwaltet wird. Sie rufen Parameterdaten aus dem Puffer ab, indem Sie [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) und [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)verwenden.

Ein Beispiel veranschaulicht, wie diese Klasse verwenden, um eine gespeicherte SQL Server-Prozedur ausgeführt und die Ausgabeparameterwerte abrufen, finden Sie die [-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) Beispielcode in die [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) Repository auf GitHub.

## <a name="requirements"></a>Anforderungen

**Header**: atldbcli.h

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)  
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)  
[CAccessor-Klasse](../../data/oledb/caccessor-class.md)  
[CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)  
[CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)  
