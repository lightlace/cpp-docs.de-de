---
title: IDBSchemaRowsetImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
- IDBSchemaRowsetImpl::CreateSchemaRowset
- ATL::IDBSchemaRowsetImpl::CreateSchemaRowset
- CreateSchemaRowset
- IDBSchemaRowsetImpl.CreateSchemaRowset
- ATL.IDBSchemaRowsetImpl.CreateSchemaRowset
- IDBSchemaRowsetImpl::SetRestrictions
- SetRestrictions
- IDBSchemaRowsetImpl.SetRestrictions
- ATL::IDBSchemaRowsetImpl::GetRowset
- ATL.IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl<SessionClass>::GetRowset
- IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl::GetRowset
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset
- GetRowset
- ATL::IDBSchemaRowsetImpl::GetSchemas
- GetSchemas
- IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- ATL.IDBSchemaRowsetImpl.GetSchemas
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- IDBSchemaRowsetImpl.GetSchemas
- IDBSchemaRowsetImpl::GetSchemas
dev_langs:
- C++
helpviewer_keywords:
- IDBSchemaRowsetImpl class
- CheckRestrictions method
- CreateSchemaRowset method
- SetRestrictions method
- GetRowset method
- GetSchemas method
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 21910a85dfecf6bd1e66b4ce0df366e3841f3c36
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572942"
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl-Klasse
Bietet die Implementierung für Schemarowsets.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
### <a name="parameters"></a>Parameter  
 *SessionClass*  
 Die Klasse, mit der `IDBSchemaRowsetImpl` geerbt wird. Diese Klasse ist in der Regel die Sitzungsklasse des Benutzers. 

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CheckRestrictions](#checkrestrictions)|Überprüft die Gültigkeit von Einschränkungen an einem Schemarowset.|  
|[CreateSchemaRowset](#createschemarowset)|Implementiert eine COM-Objekterstellerfunktion für das mit dem Vorlagenparameter angegebene Objekt.|  
|[SetRestrictions](#setrestrictions)|Gibt an, welche Einschränkungen Sie für ein bestimmtes Schemarowset unterstützen.|  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetRowset](#getrowset)|Gibt ein Schemarowset zurück.|  
|[GetSchemas](#getschemas)|Gibt eine Liste der Schemarowsets zurück, auf die [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)zugreifen kann.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse implementiert die [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\)) Schnittstelle und die vorlagenbasierte erstellerfunktion [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).  
  
 OLE DB verwendet die Schemarowsets, um Daten zu den Daten in einem Anbieter zurückzugeben. Solche Daten werden häufig als „Metadaten“ bezeichnet. Ein Anbieter muss standardmäßig immer unterstützen `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, und `DBSCHEMA_PROVIDER_TYPES`, wie in beschrieben [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\)) in die *OLE DB-Programmierreferenz*. Schemarowsets werden in einer Schemazuordnung festgelegt. Informationen zu den Schemazuordnungseinträgen finden Sie unter [SCHEMA_ENTRY](../../data/oledb/schema-entry.md).  
  
 Der OLE DB-Anbieterassistent im ATL-Objektassistenten generiert automatisch Code für die Schemarowsets in Ihrem Projekt. (Standardmäßig unterstützt der Assistent die bereits erwähnten obligatorischen Schemarowsets.) Wenn Sie einen Consumer mithilfe des ATL-Objektassistenten erstellen, verwendet der Assistent Schemarowsets, um die richtigen Daten an einen Anbieter zu binden. Wenn Sie die Schemarowsets nicht implementieren, um die richtigen Metadaten bereitzustellen, bindet der Assistent nicht die richtigen Daten.  
  
 Informationen über die Unterstützung für Schemarowsets in Ihrem Anbieter finden Sie unter [Supporting Schema Rowsets](../../data/oledb/supporting-schema-rowsets.md)(Unterstützen von Schemarowsets).  
  
 Weitere Informationen zu Schemarowsets finden Sie unter [Schemarowsets](/previous-versions/windows/desktop/ms712921\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.  

## <a name="checkrestrictions"></a> IDBSchemaRowsetImpl:: Checkrestrictions
Überprüft die Gültigkeit von Einschränkungen an einem Schemarowset.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CheckRestrictions(REFGUID rguidSchema,  
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 *rguidSchema*  
 [in] Ein Verweis auf die angeforderte Schemarowset-GUID (z. B. `DBSCHEMA_TABLES`).  
  
 *cRestrictions*  
 [in] Die Anzahl der Einschränkungen, die der Consumer für das Schemarowset übergeben hat.  
  
 *rgRestrictions*  
 [in] Ein Längenarray von *cRestrictions* von festzulegenden Einschränkungswerten. Weitere Informationen finden Sie unter der Beschreibung der *RgRestrictions* Parameter im [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie `CheckRestrictions` , um die Gültigkeit von Einschränkungen für ein Schemarowset zu überprüfen. Es überprüft die Einschränkungen für `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, und `DBSCHEMA_PROVIDER_TYPES` -Schemarowsets. Aufrufen eines Consumers bestimmt, ob aufrufen, um `IDBSchemaRowset::GetRowset` richtig ist. Wenn Sie andere als die oben aufgeführten Schemarowsets unterstützen möchten, sollten Sie Ihre eigene Funktion zum Ausführen dieser Aufgabe erstellen.  
  
 `CheckRestrictions` Bestimmt, ob der Consumer [GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) mit der richtigen Einschränkung und dem richtigen Einschränkungstyp (z. B. eine VT_BSTR nach einer Zeichenfolge), die der Anbieter unterstützt. Es bestimmt außerdem, ob die richtige Anzahl von Einschränkungen unterstützt werden. Standardmäßig fragt `CheckRestrictions` den Anbieter mittels des Aufrufs von [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) , welche Einschränkungen für ein angegebenes Rowset unterstützt werden. Es vergleicht dann die Einschränkungen vom Consumer mit den vom Anbieter unterstützten, wobei der Vergleich entweder erfolgreich ist oder fehlschlägt.  
  
 Weitere Informationen zu Schemarowsets finden Sie unter [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\)) in die *OLE DB-Programmierreferenz* im Windows SDK.  

## <a name="createschemarowset"></a> IDBSchemaRowsetImpl:: CreateSchemaRowset
Implementiert eine COM-Objekterstellerfunktion für das mit dem Vorlagenparameter angegebene Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
template template <class SchemaRowsetClass>  
HRESULT CreateSchemaRowset(IUnknown *pUnkOuter,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   SchemaRowsetClass*& pSchemaRowset);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pUnkOuter*  
 [in] Eine äußere [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) beim Aggregieren, andernfalls NULL.  
  
 *cRestrictions*  
 [in] Die Anzahl der Einschränkungen für das Schemarowset.  
  
 *rgRestrictions*  
 [in] Ein Array auf das Rowset anzuwendender `cRestrictions`**VARIANT**en.  
  
 *riid*  
 [in] Die Schnittstelle für [QueryInterface](../../atl/queryinterface.md) für in der Ausgabe `IUnknown`.  
  
 *cPropertySets*  
 [in] Die Anzahl festzulegender Eigenschaftensätze.  
  
 *rgPropertySets*  
 [in] Ein Array von [DBPROPSET](/previous-versions/windows/desktop/ms714367\(v=vs.85\)) Strukturen, die die festzulegenden Eigenschaften angeben.  
  
 *ppRowset*  
 [out] Die ausgehende `IUnknown` vom angeforderten *Riid*. Dies `IUnknown` ist eine Schnittstelle des Schemarowsetobjekts.  
  
 *pSchemaRowset*  
 [out] Ein Zeiger auf eine Instanz der Schemarowsetklasse. Dieser Parameter wird in der Regel nicht verwendet, kann jedoch verwendet werden, wenn Sie mehr Arbeit in das Schemarowset investieren müssen, bevor Sie es einem COM-Objekt übergeben. Die Lebensdauer des *pSchemaRowset* gebunden ist, indem *PpRowset*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion implementiert einen generischen Ersteller für alle Typen von Schemarowsets. In der Regel ruft der Benutzer diese Funktion nicht auf. Sie wird durch die Implementierung der Schemazuordnung aufgerufen. 

## <a name="setrestrictions"></a> IDBSchemaRowsetImpl:: SetRestrictions
Gibt an, welche Einschränkungen Sie für ein bestimmtes Schemarowset unterstützen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
void SetRestrictions(ULONG cRestrictions,  
   GUID* /* rguidSchema */,  
   ULONG* rgRestrictions);  
```  
  
#### <a name="parameters"></a>Parameter  
 *cRestrictions*  
 [in] Die Anzahl der Einschränkungen in der *RgRestrictions* Array und die Anzahl von GUIDs in der *RguidSchema* Array.  
  
 *rguidSchema*  
 [in] Ein Array von GUIDs der Schemarowsets, für die Einschränkungen abgerufen werden sollen. Jedes Arrayelement enthält die GUID eines Schemarowsets (z. B. `DBSCHEMA_TABLES`).  
  
 *rgRestrictions*  
 [in] Ein Längenarray von *cRestrictions* von festzulegenden Einschränkungswerten. Jedes Element entspricht den Einschränkungen für das Schemarowset, das mit der GUID identifiziert wird. Wenn ein Schemarowset nicht vom Anbieter unterstützt wird, wird das Element auf 0 (null) festgelegt. Andernfalls enthält der **ULONG** -Wert eine Bitmaske, die die Einschränkungen darstellt, die für dieses Schemarowset unterstützt werden. Weitere Informationen darüber, welche Einschränkungen, die einem bestimmten Schemarowset entsprechen, finden Sie in der Tabelle der Schemarowset-GUIDs in [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\)) in die *OLE DB-Programmierreferenz* in die Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Die `IDBSchemaRowset` -Objekt ruft `SetRestrictions` um zu bestimmen, welche Einschränkungen Sie für ein bestimmtes Schemarowset unterstützen (durch Aufruf von [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) über einen upcasted Zeiger). Einschränkungen ermöglichen es Consumern, nur die übereinstimmende Zeilen abzurufen (z. B. Suche nach allen Spalten in der Tabelle „MyTable“). Einschränkungen sind optional, und wenn keine unterstützt werden (Standardeinstellung), werden immer alle Daten zurückgegeben.  
  
 Die Standardimplementierung dieser Methode legt die *RgRestrictions* Arrayelemente auf 0. Überschreiben Sie die Standardeinstellung in Ihrer Sitzungsklasse, um Einschränkungen festzulegen, die vom Standard abweichen.  
  
 Informationen zum Implementieren der Schemarowset-Unterstützung finden Sie unter [Unterstützen von Schemarowsets](../../data/oledb/supporting-schema-rowsets.md).  
  
 Ein Beispiel für einen Anbieter, der Schemarowsets unterstützt, finden Sie unter den [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) Beispiel.  
  
 Weitere Informationen zu Schemarowsets finden Sie unter [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\)) in die *OLE DB-Programmierreferenz* im Windows SDK. 
  
## <a name="getrowset"></a> IDBSchemaRowsetImpl:: GetRowset
Gibt ein Schemarowset zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD (GetRowset)(IUnknown *pUnkOuter,  
   REFGUID rguidSchema,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown **ppRowset);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pUnkOuter*  
 [in] Eine äußere `IUnknown` beim Aggregieren, andernfalls NULL.  
  
 *rguidSchema*  
 [in] Ein Verweis auf die angeforderte Schemarowset-GUID (z. B. `DBSCHEMA_TABLES`).  
  
 *cRestrictions*  
 [in] Die Anzahl der Einschränkungen, die auf das Schemarowset angewendet werden sollen.  
  
 *rgRestrictions*  
 [in] Ein Array von `cRestrictions`**VARIANT**s, die die Einschränkungen darstellen.  
  
 *riid*  
 [in] Die anzufordernde IID des neu erstellten Schemarowsets.  
  
 *cPropertySets*  
 [in] Die Anzahl festzulegender Eigenschaftensätze.  
  
 *rgPropertySets*  
 [in/Out] Ein Array von [DBPROPSET](/previous-versions/windows/desktop/ms714367\(v=vs.85\)) Strukturen, die für das neu erstellte Schemarowset festgelegt.  
  
 *ppRowset*  
 [out] Ein Zeiger auf die angeforderte Schnittstelle für das neu erstellte Schemarowset.  
  
### <a name="remarks"></a>Hinweise  
 Für diese Methode muss der Benutzer eine Schemazuordnung in der Sitzungsklasse haben. Mithilfe der schemazuordnungsinformationen `GetRowset` erstellt ein angegebenes Rowsetobjekt, wenn die *RguidSchema* Parameter entspricht einem der Zuordnungseintrags-GUIDs. Unter [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) finden Sie eine Beschreibung des Zuordnungseintrags.  
  
 Finden Sie unter [IDBSchemaRowset:: GetRowset](/previous-versions/windows/desktop/ms722634\(v=vs.85\)) in das Windows SDK.  

## <a name="getschemas"></a> IDBSchemaRowsetImpl:: GetSchemas
Gibt eine Liste der Schemarowsets zurück, auf die [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)zugreifen kann.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD (GetSchema s )(ULONG * pcSchemas,  
   GUID ** prgSchemas,  
   ULONG** prgRest);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pcSchemas*  
 [out] Ein Zeiger auf eine **ULONG** , die mit der Anzahl von Schemas gefüllt ist.  
  
 *prgSchemas*  
 [out] Ein Zeiger auf ein Array von GUIDs, das mit einem Zeiger auf ein Array von Schemarowset-GUIDs gefüllt ist.  
  
 *prgRest*  
 [out] Ein Zeiger auf ein Array von **ULONG**s, das mit dem Einschränkungsarray gefüllt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt ein Array aller Schemarowsets zurück, die vom Anbieter unterstützt werden. Finden Sie unter [IDBSchemaRowset:: GetSchemas](/previous-versions/windows/desktop/ms719605\(v=vs.85\)) in das Windows SDK.  
  
 Für die Implementierung dieser Funktion muss der Benutzer eine Schemazuordnung in der Sitzungsklasse haben. Mithilfe der Schemazuordnungsinformationen antwortet die Funktion dann mit dem Array von GUIDs für die Schemas in der Zuordnung. Dies stellt die Schemas dar, die vom Anbieter unterstützt werden.  

## <a name="see-also"></a>Siehe auch  
 [IDBSchemaRowsetImpl-Klasse, Elemente](http://msdn.microsoft.com/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Schemarowset-Klassen und TypeDef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Unterstützen von Schemarowsets](../../data/oledb/supporting-schema-rowsets.md)    
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)    
 [UpdatePV](../../visual-cpp-samples.md)