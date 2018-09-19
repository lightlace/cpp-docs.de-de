---
title: CDBPropIDSet-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
- CDBPropIDSet.AddPropertyID
- CDBPropIDSet::AddPropertyID
- AddPropertyID
- ATL.CDBPropIDSet.AddPropertyID
- ATL::CDBPropIDSet::AddPropertyID
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet.operator=
- ATL.CDBPropIDSet.operator=
- ATL::CDBPropIDSet::operator=
- CDBPropIDSet::operator=
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- CDBPropIDSet class
- AddPropertyID method
- CDBPropIDSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9619ffdf9fd24bd73548fb3992084eb0a5d437a7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114474"
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet-Klasse

Erbt von der `DBPROPIDSET` -Struktur und fügt einen Konstruktor, der wichtige Felder initialisiert sowie die [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) -Zugriffsmethode.  
  
## <a name="syntax"></a>Syntax

```cpp
class CDBPropIDSet : public tagDBPROPIDSET  
```  

## <a name="requirements"></a>Anforderungen  

**Header:** atldbcli.h
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddPropertyID](#addpropertyid)|Fügt eine Eigenschaft auf den ID-Eigenschaftensatz an.|  
|[CDBPropIDSet](#cdbpropidset)|Konstruktor.|  
|[SetGUID](#setguid)|Legt fest, die GUID der Eigenschafts-ID wird.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator =](#op_equal)|Weist legen Sie den Inhalt von einer Eigenschafts-ID in eine andere.|  
  
## <a name="remarks"></a>Hinweise  

Verwenden der OLE DB-Consumer `DBPROPIDSET` Strukturen, um ein Array von Eigenschaften-IDs übergeben, für die der Consumer die Eigenschaftsinformationen abrufen möchte. In einem einzelnen angegebenen Eigenschaften [DBPROPIDSET](/previous-versions/windows/desktop/ms717981\(v=vs.85\)) Struktur zu einem Eigenschaftensatz gehören.  

## <a name="addpropertyid"></a> Cdbpropidset:: Addpropertyid

Eine Eigenschafts-ID und der ID-Eigenschaftensatz hinzugefügt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
bool AddPropertyID(DBPROPID propid) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*PROPID*<br/>
[in] Legen Sie die Eigenschafts-ID der Eigenschafts-ID hinzugefügt werden.  

## <a name="cdbpropidset"></a> Cdbpropidset:: Cdbpropidset

Der Konstruktor. Initialisiert die `rgProperties`, `cProperties`, und (optional) `guidPropertySet` Felder der [DBPROPIDSET](/previous-versions/windows/desktop/ms717981\(v=vs.85\)) Struktur.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CDBPropIDSet(const GUID& guid);  

CDBPropIDSet(const CDBPropIDSet& propidset);  

CDBPropIDSet();  
```  
  
#### <a name="parameters"></a>Parameter  

*GUID*<br/>
[in] Eine GUID, die zum Initialisieren der `guidPropertySet` Feld.  
  
*propidset*<br/>
[in] Eine andere `CDBPropIDSet` Objekt für die Copy-Konstruktion.  

## <a name="setguid"></a> Cdbpropidset:: SetGuid

Legt das Feld "GUID" der `DBPROPIDSET` Struktur.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*GUID*<br/>
[in] Eine GUID zum Festlegen der `guidPropertySet` Feld der [DBPROPIDSET](/previous-versions/windows/desktop/ms717981\(v=vs.85\)) Struktur.  
  
### <a name="remarks"></a>Hinweise  

Dieses Feld kann festgelegt werden, indem die [Konstruktor](../../data/oledb/cdbpropidset-cdbpropidset.md) ebenfalls. Rufen Sie diese Funktion, wenn Sie den Standardkonstruktor für diese Klasse verwenden.  

## <a name="op_equal"></a> Cdbpropidset:: Operator =

Weist den Inhalt von einer Eigenschafts-ID, die auf einen anderen Satz von ID-Eigenschaft festgelegt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();  
```  
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)