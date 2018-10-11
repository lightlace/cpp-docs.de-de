---
title: CStreamRowset-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8a541edb478c29fe04619dda319576717a7b9dc6
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49081844"
---
# <a name="cstreamrowset-class"></a>CStreamRowset-Klasse

Verwendet eine `CCommand` oder `CTable` Deklaration.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
### <a name="parameters"></a>Parameter  

*TAccessor*<br/>
Ein Accessor-Klasse.  

## <a name="requirements"></a>Anforderungen  

**Header:** atldbcli.h  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CStreamRowset](#cstreamrowset)|Konstruktor. Instanziiert und initialisiert die `CStreamRowset` Objekt.|  
|[Schließen](#close)|Versionen der [ISequentialStream](/previous-versions/windows/desktop/ms718035) Schnittstellenzeiger in der Klasse.|  
  
## <a name="remarks"></a>Hinweise  

Verwendung `CStreamRowset` in Ihre `CCommand` oder `CTable` Deklaration, z. B.:  
  
[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]  
  
oder  
  
[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]  
  
`ICommand::Execute` Gibt eine `ISequentialStream` -Zeiger ist, die in gespeichert ist `m_spStream`. Sie verwenden, klicken Sie dann die `Read` Methode zum Abrufen von Daten im XML-Format (Unicode-Zeichenfolge). Zum Beispiel:  
  
[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
SQL Server 2000 führt das XML-Formatierung und gibt alle Spalten und Zeilen des Rowsets als eine XML-Zeichenfolge zurück.  
  
> [!NOTE]
>  Dieses Feature funktioniert nur mit SQL Server 2000.  
  
## <a name="cstreamrowset"></a> CStreamRowset:: CStreamRowset

Instanziiert und initialisiert die `CStreamRowset` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CStreamRowset();  
```  

## <a name="close"></a> CStreamRowset:: Close

Versionen der [ISequentialStream](/previous-versions/windows/desktop/ms718035) Schnittstellenzeiger in der Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
void Close();   
```  
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)