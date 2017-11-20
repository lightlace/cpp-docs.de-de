---
title: CDynamicParameterAccessor-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
dev_langs: C++
helpviewer_keywords: CDynamicParameterAccessor class
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e30e003a054c6806994780fd4bd7b5af24f946a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor-Klasse
Ähnlich wie [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) , ruft festzulegende Parameterinformationen aber durch Aufrufen der [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) -Schnittstelle ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
 Ein Beispiel, in dem gezeigt wird, wie diese Klasse verwendet werden kann, um eine gespeicherte SQL Server-Prozedur auszuführen und die Werte der Ausgabeparameter abzurufen, finden Sie im Knowledge Base-Artikel Q058860 „Gewusst wie: Ausführen von gespeicherten Prozeduren mit CDynamicParameterAccessor“. Knowledge Base-Artikel sind in der MSDN Library-Dokumentation zu Visual Studio oder unter [http://support.microsoft.com/](http://support.microsoft.com)verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumer-Vorlagenreferenz](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)