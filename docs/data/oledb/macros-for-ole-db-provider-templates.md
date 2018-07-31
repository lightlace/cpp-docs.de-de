---
title: Makros für OLE DB-Anbietervorlagen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
- BEGIN_PROPERTY_SET
- BEGIN_PROPERTY_SET_EX
- BEGIN_PROPSET_MAP
- CHAIN_PROPERTY_SET
- END_PROPERTY_SET
- END_PROPSET_MAP
- PROPERTY_INFO_ENTRY
- PROPERTY_INFO_ENTRY_EX
- PROPERTY_INFO_ENTRY_VALUE
- BEGIN_PROVIDER_COLUMN_MAP
- END_PROVIDER_COLUMN_MAP
- PROVIDER_COLUMN_ENTRY
- PROVIDER_COLUMN_ENTRY_FIXED
- PROVIDER_COLUMN_ENTRY_GN
- PROVIDER_COLUMN_ENTRY_LENGTH
- PROVIDER_COLUMN_ENTRY_STR
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
- PROVIDER_COLUMN_ENTRY_WSTR
- BEGIN_SCHEMA_MAP
- END_SCHEMA_MAP
- SCHEMA_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, macros
- macros, OLE DB Provider Templates
- Provider Template macros (OLE DB)
- OLE DB Provider Template macros
- BEGIN_PROPERTY_SET macro
- BEGIN_PROPERTY_SET_EX macro
- BEGIN_PROPSET_MAP macro
- CHAIN_PROPERTY_SET macro
- END_PROPERTY_SET macro
- END_PROPSET_MAP macro
- PROPERTY_INFO_ENTRY macro
- PROPERTY_INFO_ENTRY_EX macro
- PROPERTY_INFO_ENTRY_VALUE macro
- BEGIN_PROVIDER_COLUMN_MAP macro
- END_PROVIDER_COLUMN_MAP macro
- PROVIDER_COLUMN_ENTRY macro
- PROVIDER_COLUMN_ENTRY_FIXED macro
- PROVIDER_COLUMN_ENTRY_GN macro
- PROVIDER_COLUMN_ENTRY_LENGTH macro
- PROVIDER_COLUMN_ENTRY_STR macro
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH macro
- PROVIDER_COLUMN_ENTRY_WSTR macro
- BEGIN_SCHEMA_MAP macro
- END_SCHEMA_MAP macro
- SCHEMA_ENTRY macro
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5c9132325af7c05980aac0d7b6b7d53958e4a2b
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338043"
---
# <a name="macros-for-ole-db-provider-templates"></a>Makros für OLE DB-Anbietervorlagen
Die Makros, die OLE DB-Vorlagen-Anbieter bieten Funktionen, die in den folgenden Kategorien:  
  
## <a name="property-set-map-macros"></a>Set Eigenschaftenzuordnungs-Makros  
  
|||  
|-|-|  
|[BEGIN_PROPERTY_SET](#begin_property_set)|Markiert den Beginn der eine Eigenschaft festgelegt.|  
|[BEGIN_PROPERTY_SET_EX](#begin_property_set_ex)|Markiert den Beginn der eine Eigenschaft festgelegt.|  
|[BEGIN_PROPSET_MAP](#begin_propset_map)|Markiert, die der Anfang einer Eigenschaft, die festlegen, können ausgeblendet oder außerhalb des Bereichs des Anbieters definiert.|  
|[CHAIN_PROPERTY_SET](#chain_property_set)|Eigenschaftengruppen verkettet miteinander.|  
|[END_PROPERTY_SET](#end_property_set)|Markiert das Ende der eine Eigenschaft festgelegt.|  
|[END_PROPSET_MAP](#end_propset_map)|Markiert das Ende der Zuordnung einer Eigenschaftensets.|  
|[PROPERTY_INFO_ENTRY](#property_info_entry)|Legt eine bestimmte Eigenschaft in einer Eigenschaft, die auf den Standardwert festgelegt.|  
|[PROPERTY_INFO_ENTRY_EX](#property_info_entry_ex)|Legt eine bestimmte Eigenschaft in einer Eigenschaft, die von Ihnen bereitgestellten Wert fest. Außerdem können Sie Optionen und Flags festzulegen.|  
|[PROPERTY_INFO_ENTRY_VALUE](#property_info_entry_value)|Legt eine bestimmte Eigenschaft in einer Eigenschaft, die von Ihnen bereitgestellten Wert fest.|  
  
## <a name="column-map-macros"></a>Spalte Eigenschaftenzuordnungs-Makros  
  
|||  
|-|-|  
|[BEGIN_PROVIDER_COLUMN_MAP](#begin_provider_column_map)|Markiert den Beginn der Zuordnungseinträge für den Anbieter.|  
|[END_PROVIDER_COLUMN_MAP](#end_provider_column_map)|Markiert das Ende der Zuordnungseinträge für den Anbieter.|  
|[PROVIDER_COLUMN_ENTRY](#provider_column_entry)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.|  
|[PROVIDER_COLUMN_ENTRY_FIXED](#provider_column_entry_fixed)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Sie können den Datentyp der Spalte angeben.|  
|[PROVIDER_COLUMN_ENTRY_GN](#provider_column_entry_gn)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Sie können die Größe, Datentyp, Genauigkeit, Dezimalstellen und Schemarowset-GUID der Spaltenwerts angeben.|  
|[PROVIDER_COLUMN_ENTRY_LENGTH](#provider_column_entry_length)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Sie können die Größe der Spalte angeben.|  
|[PROVIDER_COLUMN_ENTRY_STR](#provider_column_entry_str)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Es wird davon ausgegangen, dass der Spaltentyp eine Zeichenfolge ist.|  
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](#provider_column_entry_type_length)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. PROVIDER_COLUMN_ENTRY_LENGTH wie, sondern auch Ihnen die Angabe der Datentyp der Spalte sowie der Größe.|  
|[PROVIDER_COLUMN_ENTRY_WSTR](#provider_column_entry_wstr)|Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden. Es wird davon ausgegangen, dass der Spaltentyp Unicode-Zeichenfolge ist.|  
  
## <a name="schema-rowset-macros"></a>Schema-Rowset-Makros  
  
|||  
|-|-|  
|[BEGIN_SCHEMA_MAP](#begin_schema_map)|Markiert den Beginn einer Schema-Zuordnung.|  
|[END_SCHEMA_MAP](#end_schema_map)|Markiert das Ende einer Zuordnung Schema.|  
|[SCHEMA_ENTRY](#schema_entry)|Ordnet eine GUID einer Klasse.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  

### <a name="begin_property_set"></a> BEGIN_PROPERTY_SET
Markiert, die der Anfang einer Eigenschaft in einer Eigenschaft festgelegt-Zuordnung festgelegt.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
BEGIN_PROPERTY_SET(guid)  
```  
  
#### <a name="parameters"></a>Parameter  
 *GUID*  
 [in] Die GUID-Eigenschaft.  
  
#### <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="begin_property_set_ex"></a> BEGIN_PROPERTY_SET_EX
Markiert, die der Anfang einer Eigenschaft in einer Eigenschaft festgelegt-Zuordnung festgelegt.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
BEGIN_PROPERTY_SET_EX(guid, flags)  
```  
  
#### <a name="parameters"></a>Parameter  
 *GUID*  
 [in] Die GUID-Eigenschaft.  
  
 *flags*  
 [in] UPROPSET_HIDDEN für eine beliebige Eigenschaftensätze, die Sie nicht möchten, verfügbar zu machen oder UPROPSET_PASSTHROUGH für einen Anbieter mit dem Verfügbarmachen von Eigenschaften, die außerhalb des Bereichs des Anbieters definiert.  
  
#### <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="begin_propset_map"></a> BEGIN_PROPSET_MAP
Ein Festlegen der Anfang der Eigenschaft-Zuordnungseinträge.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
BEGIN_PROPSET_MAP(Class)  
```  
  
#### <a name="parameters"></a>Parameter  
 *Klasse*  
 [in] Die Klasse, die in der diese Eigenschaft festgelegt angegeben wird. Eine Eigenschaft festgelegt, kann in den folgenden OLE DB-Objekten angegeben werden:  
  
-   [Datenquellenobjekte](https://msdn.microsoft.com/library/ms721278.aspx)  
  
-   [Session-Objekte](https://msdn.microsoft.com/library/ms711572.aspx)  
  
-   [Befehle](https://msdn.microsoft.com/library/ms724608.aspx)  
  
#### <a name="example"></a>Beispiel  
 Hier ist eine Beispiel-eigenschaftenzuordnung Satz ein:  
  
 [!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]  

### <a name="chain_property_set"></a> CHAIN_PROPERTY_SET
Dieses Makro wird Eigenschaftengruppen miteinander verkettet.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
CHAIN_PROPERTY_SET(ChainClass)  
```  
  
#### <a name="parameters"></a>Parameter  
 *ChainClass*  
 [in] Der Name der Klasse in der von Ketteneigenschaften für. Dies ist eine Klasse, die vom ATL-Projektassistenten, die bereits eine Zuordnung (z. B. eine Sitzung oder den Befehl Objekt Quellklasse) enthält.  
  
#### <a name="remarks"></a>Hinweise  
 Sie können einen Eigenschaftensatz von einer anderen Klasse, um eine eigene Klasse verkettet und dann den Zugriff auf die Eigenschaften direkt von Ihrer Klasse.  
  
> [!CAUTION]
>  Verwenden Sie dieses Makro nur selten auf. Nicht ordnungsgemäße sprachnutzung kann dazu führen, dass einen Consumer die OLE DB-Konformitätstests fehlschlägt.  

### <a name="end_property_set"></a> END_PROPERTY_SET
Markiert das Ende der eine Eigenschaft festgelegt.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
END_PROPERTY_SET(guid)  
```  
  
#### <a name="parameters"></a>Parameter  
 *GUID*  
 [in] Die GUID-Eigenschaft.  
  
#### <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="end_propset_map"></a> END_PROPSET_MAP
Markiert das Ende der Eigenschaft legen Sie-Zuordnungseinträge.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
END_PROPSET_MAP()  
```  
  
#### <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="property_info_entry"></a> PROPERTY_INFO_ENTRY
Stellt eine bestimmte Eigenschaft in einem Eigenschaftensatz dar.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
PROPERTY_INFO_ENTRY(dwPropID)  
```  
  
#### <a name="parameters"></a>Parameter  
 *dwPropID*  
 [in] Ein [DBPROPID](https://msdn.microsoft.com/library/ms723882.aspx) -Wert, der in Verbindung mit der Eigenschaft verwendet werden kann soll, GUID, die eine Eigenschaft zu identifizieren.  
  
#### <a name="remarks"></a>Hinweise  
 Dieses Makro legt den Wert der Eigenschaft vom Typ `DWORD` auf einen in ATLDB.H definierten Standardwert fest. Verwenden Sie [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md), um die Eigenschaft auf einen Wert Ihrer Wahl festzulegen. Festlegen der [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4) und [DBPROPFLAGS](https://msdn.microsoft.com/library/ms724342.aspx) verwenden Sie für die Eigenschaft zur gleichen Zeit [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).  
  
#### <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="property_info_entry_ex"></a> PROPERTY_INFO_ENTRY_EX
Stellt eine bestimmte Eigenschaft in einem Eigenschaftensatz dar.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID, vt, dwFlags, value, options)  
```  
  
#### <a name="parameters"></a>Parameter  
 *dwPropID*  
 [in] Ein [DBPROPID](https://msdn.microsoft.com/library/ms723882.aspx) -Wert, der in Verbindung mit der Eigenschaft verwendet werden kann soll, GUID, die eine Eigenschaft zu identifizieren.  
  
 *vt*  
 [in] Die [VARTYPE](http://msdn.microsoft.com/317b911b-1805-402d-a9cb-159546bc88b4) dieses Eigenschaftseintrags.  
  
 *dwFlags*  
 [in] Ein [DBPROPFLAGS](https://msdn.microsoft.com/library/ms724342.aspx) Wert, der diesen Eigenschaftseintrag beschreibt.  
  
 *Wert*  
 [in] Der Eigenschaftswert von Typ `DWORD`.  
  
 *Optionen*  
 DBPROPOPTIONS_REQUIRED oder DBPROPOPTIONS_SETIFCHEAP. In der Regel ein Anbieter muss nicht festgelegt *Optionen* , da er vom Consumer festgelegt ist.  
  
#### <a name="remarks"></a>Hinweise  
 Mit diesem Makro können Sie den Wert der Eigenschaft des Typs `DWORD` sowie Optionen und Flags direkt angeben. Um lediglich einen in ATLDB.H definierten Standardwert für eine Eigenschaft festzulegen, verwenden Sie [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Um einen Wert Ihrer Wahl für eine Eigenschaft festzulegen, verwenden Sie [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md).  
  
#### <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="property_info_entry_value"></a> PROPERTY_INFO_ENTRY_VALUE
Stellt eine bestimmte Eigenschaft in einem Eigenschaftensatz dar.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
PROPERTY_INFO_ENTRY_VALUE(dwPropID, value)  
```  
  
#### <a name="parameters"></a>Parameter  
 *dwPropID*  
 [in] Ein [DBPROPID](https://msdn.microsoft.com/library/ms723882.aspx) -Wert, der in Verbindung mit der Eigenschaft verwendet werden kann soll, GUID, die eine Eigenschaft zu identifizieren.  
  
 *Wert*  
 [in] Der Eigenschaftswert von Typ `DWORD`.  
  
#### <a name="remarks"></a>Hinweise  
 Mit diesem Makro können Sie den Wert der Eigenschaft des Typs direkt angeben `DWORD`. Um die Eigenschaft in ATLDB definierten Standardwert fest. H, Verwendung [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Verwenden Sie zum Festlegen der Wert, Flags und Optionen für die Eigenschaft [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).  
  
#### <a name="example"></a>Beispiel  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="begin_provider_column_map"></a> BEGIN_PROVIDER_COLUMN_MAP
Markiert den Beginn der Zuordnungseinträge für den Anbieter.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
BEGIN_PROVIDER_COLUMN_MAP(theClass)  
```  
  
#### <a name="parameters"></a>Parameter  
 *theClass*  
 [in] Der Name der Klasse, die, der diese Zuordnung gehört.  
  
#### <a name="example"></a>Beispiel  
 Hier ist eine Beispiel-anbieterzuordnung von Spalte:  
  
 [!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]  

### <a name="end_provider_column_map"></a> END_PROVIDER_COLUMN_MAP
Markiert das Ende der Zuordnungseinträge für den Anbieter.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
END_PROVIDER_COLUMN_MAP()  
```  
  
#### <a name="example"></a>Beispiel  
 Finden Sie unter [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).  

### <a name="provider_column_entry"></a> PROVIDER_COLUMN_ENTRY
Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
PROVIDER_COLUMN_ENTRY (name, ordinal, member)  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 [in] Name der Spalte.  
  
 *Ordinal*  
 [in] Die Nummer der Spalte. Wenn die Spalte eine Lesezeichenspalte ist, muss die Nummer der Spalte nicht 0 sein.  
  
 *Member*  
 [in] Die Membervariable in `dataClass` der Spalte entspricht.  

### <a name="provider_column_entry_fixed"></a> PROVIDER_COLUMN_ENTRY_FIXED
Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
PROVIDER_COLUMN_ENTRY_FIXED(name, ordinal, dbtype, member)  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 [in] Name der Spalte.  
  
 *Ordinal*  
 [in] Die Nummer der Spalte. Wenn die Spalte eine Lesezeichenspalte ist, muss die Nummer der Spalte nicht 0 sein.  
  
 *DbType*  
 [in] Der Datentyp im [DBTYPE](https://msdn.microsoft.com/library/ms711251.aspx).  
  
 *Member*  
 [in] Die Membervariable in `dataClass` , die die Daten speichert.  
  
#### <a name="remarks"></a>Hinweise  
 Können Sie den Datentyp der Spalte anzugeben.  
  
#### <a name="example"></a>Beispiel  
 Finden Sie unter [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).  

### <a name="provider_column_entry_gn"></a> PROVIDER_COLUMN_ENTRY_GN
Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
PROVIDER_COLUMN_ENTRY_GN (name, ordinal, flags, colSize, dbtype, precision, scale, guid)  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 [in] Name der Spalte.  
  
 *Ordinal*  
 [in] Die Nummer der Spalte. Wenn die Spalte eine Lesezeichenspalte ist, muss die Nummer der Spalte nicht 0 sein.  
  
 *flags*  
 [in] Gibt an, wie Daten zurückgegeben werden. Finden Sie unter den `dwFlags` Beschreibung im [DBBINDING-Strukturen](https://msdn.microsoft.com/library/ms716845.aspx).  
  
 *colSize*  
 [in] Die Größe der Spalte.  
  
 *DbType*  
 [in] Gibt den Datentyp des Werts an. Finden Sie unter den `wType` Beschreibung im [DBBINDING-Strukturen](https://msdn.microsoft.com/library/ms716845.aspx).  
  
 *precision*  
 [in] Gibt die Genauigkeit verwenden, beim Abrufen von Daten, wenn *DbType* DBTYPE_NUMERIC oder DBTYPE_DECIMAL ist. Finden Sie unter den `bPrecision` Beschreibung im [DBBINDING-Strukturen](https://msdn.microsoft.com/library/ms716845.aspx).  
  
 *Skalieren*  
 [in] Gibt die zu verwendende beim Abrufen von Daten, wenn DbType DBTYPE_NUMERIC oder DBTYPE_DECIMAL Skala an. Finden Sie unter den `bScale` Beschreibung im [DBBINDING-Strukturen](https://msdn.microsoft.com/library/ms716845.aspx).  
  
 *GUID*  
 Ein Schemarowset-GUID. Finden Sie unter [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) in die *OLE DB-Programmierreferenz* eine Liste der Schemarowsets und die GUIDs.  
  
#### <a name="remarks"></a>Hinweise  
 Ermöglicht Ihnen die Angabe der Größe, Datentyp, Genauigkeit, Dezimalstellen und Schemarowset-GUID der Spaltenwerts.  

### <a name="provider_column_entry_length"></a> PROVIDER_COLUMN_ENTRY_LENGTH
Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
PROVIDER_COLUMN_ENTRY_LENGTH(name, ordinal, size, member)  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 [in] Name der Spalte.  
  
 *Ordinal*  
 [in] Die Nummer der Spalte. Wenn die Spalte eine Lesezeichenspalte ist, muss die Nummer der Spalte nicht 0 sein.  
  
 *size*  
 [in] Die Spaltengröße in Bytes.  
  
 *Member*  
 [in] Die Membervariable in `dataClass` , speichert die Daten der Spalte.  
  
#### <a name="remarks"></a>Hinweise  
 Können Sie die Spaltengröße anzugeben.  
  
#### <a name="example"></a>Beispiel  
 Finden Sie unter [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md). 

### <a name="provider_column_entry_str"></a> PROVIDER_COLUMN_ENTRY_STR
Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
PROVIDER_COLUMN_ENTRY_STR(name, ordinal, member)  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 [in] Name der Spalte.  
  
 *Ordinal*  
 [in] Die Nummer der Spalte. Wenn die Spalte eine Lesezeichenspalte ist, muss die Nummer der Spalte nicht 0 sein.  
  
 *Member*  
 [in] Die Membervariable in der Datenklasse, die Daten speichert.  
  
#### <a name="remarks"></a>Hinweise  
 Wenn die Spaltendaten als angesehen werden, verwenden Sie dieses Makro [DBTYPE_STR](https://msdn.microsoft.com/library/ms711251.aspx).  
  
#### <a name="example"></a>Beispiel  
 Finden Sie unter [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).   

### <a name="provider_column_entry_type_length"></a> PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(name, ordinal, dbtype, size, member)  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 [in] Name der Spalte.  
  
 *Ordinal*  
 [in] Die Nummer der Spalte. Wenn die Spalte eine Lesezeichenspalte ist, muss die Nummer der Spalte nicht 0 sein.  
  
 *DbType*  
 [in] Der Datentyp im [DBTYPE](https://msdn.microsoft.com/library/ms711251.aspx).  
  
 *size*  
 [in] Die Spaltengröße in Bytes.  
  
 *Member*  
 [in] Die Membervariable in der Datenklasse, die Daten speichert.  
  
#### <a name="remarks"></a>Hinweise  
 Ähnlich wie [PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md) ermöglicht aber auch Sie Datentyp der Spalte sowie die Größe angeben.  

### <a name="provider_column_entry_wstr"></a> PROVIDER_COLUMN_ENTRY_WSTR
Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
PROVIDER_COLUMN_ENTRY_WSTR(name, ordinal, member)  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 [in] Name der Spalte.  
  
 *Ordinal*  
 [in] Die Nummer der Spalte. Wenn die Spalte eine Lesezeichenspalte ist, muss die Nummer der Spalte nicht 0 sein.  
  
 *Member*  
 [in] Die Membervariable in der Datenklasse, die Daten speichert.  
  
#### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro aus, wenn die Spaltendaten ist eine Null-terminierte Unicode-Zeichenfolge, [DBTYPE_WSTR](https://msdn.microsoft.com/library/ms711251.aspx).  

### <a name="begin_schema_map"></a> BEGIN_SCHEMA_MAP
Kennzeichnet den Anfang einer schemazuordnung.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
BEGIN_SCHEMA_MAP(SchemaClass);  
```  
  
#### <a name="parameters"></a>Parameter  
 *SchemaClass*  
 Die Klasse, die die Zuordnung enthält. Dies wird in der Regel die Sitzungsklasse sein.  
  
#### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) im Windows SDK für Weitere Informationen zu Schemarowsets.  

### <a name="end_schema_map"></a> END_SCHEMA_MAP
Kennzeichnet das Ende der schemazuordnung.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
END_SCHEMA_MAP()  
```  
  
#### <a name="see-also"></a>Siehe auch  
 [IDBSchemaRowsetImpl-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)

### <a name="schema_entry"></a> SCHEMA_ENTRY
Ordnet eine GUID einer Klasse.  
  
#### <a name="syntax"></a>Syntax  
  
```cpp
SCHEMA_ENTRY(guid,  
   rowsetClass);   
```  
  
#### <a name="parameters"></a>Parameter  
 *GUID*  
 Ein Schemarowset-GUID. Finden Sie unter [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) in die *OLE DB-Programmierreferenz* eine Liste der Schemarowsets und die GUIDs.  
  
 *rowsetClass*  
 Die Klasse, die erstellt werden, um die Schemarowsets darstellen.  
  
#### <a name="remarks"></a>Hinweise  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) können Sie die Abfrage der Zuordnung für eine Liste von GUIDs oder ein Rowset erstellt, wenn sie eine GUID angegeben wird. Das Schemarowset `IDBSchemaRowsetImpl` erstellt ist vergleichbar mit einem Standard `CRowsetImpl`-abgeleiteten Klasse, außer es bereitstellen, muss ein `Execute` Methode, folgenden Signatur besitzt:  
  
```cpp  
HRESULT Execute (LONG* pcRowsAffected,  
    ULONG cRestrictions,  
    const VARIANT* rgRestrictions);  
```  
  
 Dies `Execute` Funktion füllt die Rowset-Daten. ATL-Projektassistenten erstellt, wie in beschrieben [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) in die *OLE DB-Programmierreferenz*, drei ersten Schemarowsets in das Projekt, für jedes der drei obligatorische OLE DB-Schemas:  
  
-   DBSCHEMA_TABLES  
  
-   DBSCHEMA_COLUMNS  
  
-   DBSCHEMA_PROVIDER_TYPES  
  
 Der Assistent fügt auch drei entsprechende Einträge in der schemazuordnung hinzu. Finden Sie unter [erstellen einen OLE DB-Anbieter für Vorlage](../../data/oledb/creating-an-ole-db-provider.md) für Weitere Informationen zum Verwenden des Assistenten zum Erstellen eines Anbieters.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbieter](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen einen OLE DB-Anbieter](../../data/oledb/creating-an-ole-db-provider.md)   
 [Referenz der OLE DB-Vorlagen](../../data/oledb/ole-db-provider-templates-reference.md)    
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   