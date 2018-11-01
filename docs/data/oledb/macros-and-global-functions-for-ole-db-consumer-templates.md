---
title: Makros und globale Funktionen für OLE DB-Consumervorlagen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
- BEGIN_ACCESSOR
- BEGIN_ACCESSOR_MAP
- END_ACCESSOR
- END_ACCESSOR_MAP
- BEGIN_COLUMN_MAP
- BLOB_ENTRY
- BLOB_ENTRY_LENGTH
- BLOB_ENTRY_LENGTH_STATUS
- BLOB_ENTRY_STATUS
- BLOB_NAME
- BLOB_NAME_LENGTH
- BLOB_NAME_LENGTH_STATUS
- BLOB_NAME_STATUS
- BOOKMARK_ENTRY
- COLUMN_ENTRY
- COLUMN_ENTRY_EX
- COLUMN_ENTRY_LENGTH
- COLUMN_ENTRY_LENGTH_STATUS
- COLUMN_ENTRY_PS
- COLUMN_ENTRY_PS_LENGTH
- COLUMN_ENTRY_PS_LENGTH_STATUS
- COLUMN_ENTRY_PS_STATUS
- COLUMN_ENTRY_STATUS
- COLUMN_ENTRY_TYPE
- COLUMN_ENTRY_TYPE_SIZE
- COLUMN_NAME
- COLUMN_NAME_EX
- COLUMN_NAME_LENGTH
- COLUMN_NAME_LENGTH_STATUS
- COLUMN_NAME_PS
- COLUMN_NAME_PS_LENGTH
- COLUMN_NAME_PS_LENGTH_STATUS
- COLUMN_NAME_PS_STATUS
- COLUMN_NAME_STATUS
- COLUMN_NAME_TYPE
- COLUMN_NAME_TYPE_PS
- COLUMN_NAME_TYPE_SIZE
- COLUMN_NAME_TYPE_STATUS
- END_COLUMN_MAP
- DEFINE_COMMAND
- DEFINE_COMMAND_EX
- BEGIN_PARAM_MAP
- END_PARAM_MAP
- SET_PARAM_TYPE
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
- AtlTraceErrorRecords function
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR_MAP macro
- END_ACCESSOR macro
- END_ACCESSOR_MAP macro
- BEGIN_COLUMN_MAP macro
- BLOB_ENTRY macro
- BLOB_ENTRY_LENGTH macro
- BLOB_ENTRY_LENGTH_STATUS macro
- BLOB_ENTRY_STATUS macro
- BLOB_NAME macro
- BLOB_NAME_LENGTH macro
- BLOB_NAME_LENGTH_STATUS macro
- BLOB_NAME_STATUS macro
- BOOKMARK_ENTRY macro
- COLUMN_ENTRY macro
- COLUMN_ENTRY_EX macro
- COLUMN_ENTRY_LENGTH macro
- COLUMN_ENTRY_LENGTH_STATUS macro
- COLUMN_ENTRY_PS macro
- COLUMN_ENTRY_PS_LENGTH macro
- COLUMN_ENTRY_PS_LENGTH_STATUS macro
- COLUMN_ENTRY_PS_STATUS macro
- COLUMN_ENTRY_STATUS macro
- COLUMN_ENTRY_TYPE macro
- COLUMN_ENTRY_TYPE_SIZE macro
- COLUMN_NAME macro
- COLUMN_NAME_EX macro
- COLUMN_NAME_LENGTH macro
- COLUMN_NAME_LENGTH_STATUS macro
- COLUMN_NAME_PS macro
- COLUMN_NAME_PS_LENGTH macro
- COLUMN_NAME_PS_LENGTH_STATUS macro
- COLUMN_NAME_PS_STATUS macro
- COLUMN_NAME_STATUS macro
- COLUMN_NAME_TYPE macro
- COLUMN_NAME_TYPE_PS macro
- COLUMN_NAME_TYPE_SIZE macro
- COLUMN_NAME_TYPE_STATUS macro
- END_COLUMN_MAP macro
- DEFINE_COMMAND macro
- DEFINE_COMMAND_EX macro
- BEGIN_PARAM_MAP macro
- END_PARAM_MAP macro
- SET_PARAM_TYPE macro
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8077714292929b66d7e03014aa567f524a2709dc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069166"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>Makros und globale Funktionen für OLE-Consumervorlagen

Die OLE DB-Consumervorlagen gehören die folgenden Makros und globale Funktionen:

## <a name="global-functions"></a>Globale Funktionen

|||
|-|-|
|[AtlTraceErrorRecords](#atltraceerrorrecords)|Gibt OLE DB-Fehlerdatensatz Informationen auf dem Sicherungsmedium an, wenn ein Fehler zurückgegeben wird.|

## <a name="accessor-map-macros"></a>Accessor-Zuordnungs-Makros

|||
|-|-|
|[BEGIN_ACCESSOR](#begin_accessor)|Markiert den Beginn eines Eintrags für die Zugriffsmethode.|
|[BEGIN_ACCESSOR_MAP](#begin_accessor_map)|Markiert den Beginn der Accessor-Zuordnungseinträge.|
|[END_ACCESSOR](#end_accessor)|Markiert das Ende eines Eintrags für die Zugriffsmethode.|
|[END_ACCESSOR_MAP](#end_accessor_map)|Markiert das Ende der Accessor-Zuordnungseinträge.|

## <a name="column-map-macros"></a>Spalte Eigenschaftenzuordnungs-Makros

|||
|-|-|
|[BEGIN_COLUMN_MAP](#begin_column_map)|Markiert den Beginn der Zuordnungseintrags-Spalte in die Benutzerdatensatz-Klasse.|
|[BLOB_ENTRY](#blob_entry)|Wird verwendet, um ein binary large Object (BLOB) zu binden.|
|[BLOB_ENTRY_LENGTH](#blob_entry_length)|Gibt die Länge der BLOB-Spalte.|
|[BLOB_ENTRY_LENGTH_STATUS](#blob_entry_length_status)|Gibt die Länge und den Status der BLOB-Spalte.|
|[BLOB_ENTRY_STATUS](#blob_entry_status)|Meldet den Status der BLOB-Spalte.|
|[BLOB_NAME](#blob_name)|Verwendet, um ein großes binäres Objekt anhand des Spaltennamens zu binden.|
|[BLOB_NAME_LENGTH](#blob_name_length)|Gibt die Länge der BLOB-Spalte.|
|[BLOB_NAME_LENGTH_STATUS](#blob_name_length_status)|Gibt die Länge und den Status der BLOB-Spalte.|
|[BLOB_NAME_STATUS](#blob_name_status)|Meldet den Status der BLOB-Spalte.|
|[BOOKMARK_ENTRY](#bookmark_entry)|Stellt einen Lesezeicheneintrag für das Rowset dar. Ein Lesezeicheneintrag ist eine besondere Art von Eintrag in der Spalte.|
|[COLUMN_ENTRY](#column_entry)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank dar.|
|[COLUMN_ENTRY_EX](#column_entry_ex)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt *Typ*, *Länge*, *Genauigkeit*, *Skalierung*, und *Status* Parameter.|
|[COLUMN_ENTRY_LENGTH](#column_entry_length)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt die *Länge* Variable.|
|[COLUMN_ENTRY_LENGTH_STATUS](#column_entry_length_status)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt *Status* und *Länge* Parameter.|
|[COLUMN_ENTRY_PS](#column_entry_ps)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt *Genauigkeit* und *Skalierung* Parameter.|
|[COLUMN_ENTRY_PS_LENGTH](#column_entry_ps_length)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt die *Länge* Variable *Genauigkeit* und *Skalierung* Parameter.|
|[COLUMN_ENTRY_PS_LENGTH_STATUS](#column_entry_ps_length_status)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt *Status* und *Länge* Variablen *Genauigkeit* und *Skalierung* Parameter.|
|[COLUMN_ENTRY_PS_STATUS](#column_entry_ps_status)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt die *Status* Variable *Genauigkeit* und *Skalierung* Parameter.|
|[COLUMN_ENTRY_STATUS](#column_entry_status)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt die *Status* Variable.|
|[COLUMN_ENTRY_TYPE](#column_entry_type)|Stellt eine Bindung zu einer bestimmten Spalte in der Datenbank dar. Unterstützt *Typ* Parameter.|
|[COLUMN_ENTRY_TYPE_SIZE](#column_entry_type_size)|Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt *Typ* und *Größe* Parameter.|
|[COLUMN_NAME](#column_name)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar.|
|[COLUMN_NAME_EX](#column_name_ex)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe von Datentyp, Größe, Genauigkeit, Dezimalstellen, Länge der Spalte und Status in der Spalte.|
|[COLUMN_NAME_LENGTH](#column_name_length)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe der Länge der Spalte.|
|[COLUMN_NAME_LENGTH_STATUS](#column_name_length_status)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Spezifikation der Spaltenlänge und Status.|
|[COLUMN_NAME_PS](#column_name_ps)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe von Genauigkeit und Dezimalstellenanzahl.|
|[COLUMN_NAME_PS_LENGTH](#column_name_ps_length)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe von Genauigkeit, Dezimalstellen und Spalte Länge.|
|[COLUMN_NAME_PS_LENGTH_STATUS](#column_name_ps_length_status)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe von Genauigkeit, Dezimalstellen, Länge der Spalte und Status in der Spalte.|
|[COLUMN_NAME_PS_STATUS](#column_name_ps_status)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe von Genauigkeit, Dezimalstellen und Spalte Status.|
|[COLUMN_NAME_STATUS](#column_name_status)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe von Status in der Spalte.|
|[COLUMN_NAME_TYPE](#column_name_type)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe des Datentyps.|
|[COLUMN_NAME_TYPE_PS](#column_name_type_ps)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe von Datentyp, Genauigkeit und Dezimalstellen.|
|[COLUMN_NAME_TYPE_SIZE](#column_name_type_size)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe von Datentyp und Größe.|
|[COLUMN_NAME_TYPE_STATUS](#column_name_type_status)|Stellt eine Bindung an eine bestimmte Spalte in der Datenbank nach Name dar. Unterstützt die Angabe von Typ und der Spalte Status von Daten.|
|[END_COLUMN_MAP](#end_column_map)|Markiert das Ende der Zuordnungseintrags-Spalte.|

## <a name="command-macros"></a>Befehlsmakros

|||
|-|-|
|[DEFINE_COMMAND](#define_command)|Gibt den Befehl, der verwendet wird, um das Rowset zu erstellen, bei Verwendung der [CCommand](../../data/oledb/ccommand-class.md) Klasse. Akzeptiert nur Zeichenfolgen-Datentypen, die Übereinstimmung des angegebenen Anwendungstyps (ANSI oder Unicode). Es wird empfohlen, die Verwendung von [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) statt DEFINE_COMMAND.|
|[DEFINE_COMMAND_EX](#define_command_ex)|Gibt den Befehl, der verwendet wird, um das Rowset zu erstellen, bei Verwendung der [CCommand](../../data/oledb/ccommand-class.md) Klasse. Unterstützt die ANSI- und Unicode-Anwendungen.|

## <a name="parameter-map-macros"></a>Parameter-Zuordnungs-Makros

|||
|-|-|
|[BEGIN_PARAM_MAP](#begin_param_map)|Markiert den Beginn der Zuordnungseintrags-Parameter in die Benutzerdatensatz-Klasse.|
|[END_PARAM_MAP](#end_param_map)|Markiert das Ende der Zuordnungseintrags-Parameter.|
|[SET_PARAM_TYPE](#set_param_type)|Gibt an, COLUMN_ENTRY-Makros, die die SET_PARAM_TYPE-Makro als Eingabe-, Ausgabe- oder Eingabe/Ausgabe zu folgen.|

### <a name="atltraceerrorrecords"></a> AtlTraceErrorRecords

Gibt OLE DB-Fehlerdatensatz Informationen auf dem Sicherungsmedium an, wenn ein Fehler zurückgegeben wird.

#### <a name="syntax"></a>Syntax

```cpp
inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);
```

#### <a name="parameters"></a>Parameter

*hErr*<br/>
[in] Ein HRESULT, der von einer OLE DB-Consumervorlagen Memberfunktion zurückgegeben wird.

#### <a name="remarks"></a>Hinweise

Wenn *hErr* ist nicht S_OK, `AtlTraceErrorRecords` gibt OLE DB-Fehlerdatensatz Informationen auf dem Sicherungsmedium (die **Debuggen** Registerkarte dem Fenster "Ausgabe" oder eine Datei). Die Error-Datensatzes von Informationen vom Anbieter abgerufen wird, enthält die Nummer der Zeile, Quelle, Beschreibung, Hilfe, Kontext und GUID für jeden Eintrag der Fehler. `AtlTraceErrorRecords` gibt diese Informationen nur in Debug-Builds. In Releasebuilds ist es sich um einen leeren Stub, der Sie optimiert ist.

#### <a name="see-also"></a>Siehe auch

[CDBErrorInfo-Klasse](../../data/oledb/cdberrorinfo-class.md)

### <a name="begin_accessor"></a> BEGIN_ACCESSOR

Markiert den Beginn eines Eintrags für die Zugriffsmethode.

#### <a name="syntax"></a>Syntax

```cpp
BEGIN_ACCESSOR(num, bAuto)
```

#### <a name="parameters"></a>Parameter

*num*<br/>
[in] Die Anzahl der NULL-Offset für den Accessor in dieser accessorzuordnung.

*bAuto*<br/>
[in] Gibt an, ob dieser Accessor einen Accessor für die automatische oder manuelle-Accessor. Wenn **"true"**, der Accessor ist automatisch, wenn **"false"**, der Accessor ist manuell. Ein Accessor automatisch bedeutet, dass es sich bei Daten auf Move-Vorgänge für Sie abgerufen werden.

#### <a name="remarks"></a>Hinweise

Bei mehreren Accessoren für ein Rowset müssen Sie BEGIN_ACCESSOR_MAP geben an, und die BEGIN_ACCESSOR-Makro für jeden einzelnen Accessor verwenden. Das BEGIN_ACCESSOR-Makro wird mit dem END_ACCESSOR-Makro abgeschlossen. Das BEGIN_ACCESSOR_MAP-Makro wird mit dem END_ACCESSOR_MAP-Makro abgeschlossen.

#### <a name="example"></a>Beispiel

Finden Sie unter [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="begin_accessor_map"></a> BEGIN_ACCESSOR_MAP

Markiert den Beginn der Accessor-Zuordnungseinträge.

#### <a name="syntax"></a>Syntax

```cpp
BEGIN_ACCESSOR_MAP(x, num)
```

#### <a name="parameters"></a>Parameter

*w*<br/>
[in] Der Name der Benutzerdatensatzklasse.

*num*<br/>
[in] Die Anzahl der Accessoren in dieser Accessorzuordnung.

#### <a name="remarks"></a>Hinweise

Bei mehreren Accessoren für ein Rowset müssen Sie BEGIN_ACCESSOR_MAP am Anfang geben an, und die BEGIN_ACCESSOR-Makro für jeden einzelnen Accessor verwenden. Das BEGIN_ACCESSOR-Makro wird mit dem END_ACCESSOR-Makro abgeschlossen. Die accessorzuordnung wird mit dem END_ACCESSOR_MAP-Makro abgeschlossen.

Wenn es nur einen Accessor im Benutzerdatensatz gibt, verwenden Sie das Makro [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).

#### <a name="example"></a>Beispiel

```cpp
class CArtistsAccessor
{
public:
// Data Elements
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];
   short m_nAge;

// Output binding map
BEGIN_ACCESSOR_MAP(CArtistsAccessor, 2)
   BEGIN_ACCESSOR(0, true)
      COLUMN_ENTRY(1, m_szFirstName)
      COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false) // Not an auto accessor
      COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsAccessor, L" \
   SELECT \
      FirstName, \
      LastName, \
      Age \
      FROM Artists")
};
```

### <a name="end_accessor"></a> END_ACCESSOR

Markiert das Ende eines Eintrags für die Zugriffsmethode.

#### <a name="syntax"></a>Syntax

```cpp
END_ACCESSOR()
```

#### <a name="remarks"></a>Hinweise

Für mehrere Accessoren für ein Rowset müssen Sie BEGIN_ACCESSOR_MAP geben an, und die BEGIN_ACCESSOR-Makro für jeden einzelnen Accessor verwenden. Das BEGIN_ACCESSOR-Makro wird mit dem END_ACCESSOR-Makro abgeschlossen. Das BEGIN_ACCESSOR_MAP-Makro wird mit dem END_ACCESSOR_MAP-Makro abgeschlossen.

#### <a name="example"></a>Beispiel

Finden Sie unter [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="end_accessor_map"></a> END_ACCESSOR_MAP

Markiert das Ende der Accessor-Zuordnungseinträge.

#### <a name="syntax"></a>Syntax

```cpp
END_ACCESSOR_MAP()
```

#### <a name="remarks"></a>Hinweise

Für mehrere Accessoren für ein Rowset müssen Sie BEGIN_ACCESSOR_MAP geben an, und die BEGIN_ACCESSOR-Makro für jeden einzelnen Accessor verwenden. Das BEGIN_ACCESSOR-Makro wird mit dem END_ACCESSOR-Makro abgeschlossen. Das BEGIN_ACCESSOR_MAP-Makro wird mit dem END_ACCESSOR_MAP-Makro abgeschlossen.

#### <a name="example"></a>Beispiel

Finden Sie unter [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="begin_column_map"></a> BEGIN_COLUMN_MAP

Kennzeichnet den Anfang eines Spaltenzuordnungseintrags.

#### <a name="syntax"></a>Syntax

```cpp
BEGIN_COLUMN_MAP(x)
```

#### <a name="parameters"></a>Parameter

*w*<br/>
[in] Der Name der Benutzerdatensatzklasse, abgeleitet aus `CAccessor`.

#### <a name="remarks"></a>Hinweise

Dieses Makro wird im Fall eines einzelnen Accessors in einem Rowset verwendet. Wenn Sie über mehrere Accessoren in einem Rowset verfügen, verwenden Sie [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

Das BEGIN_COLUMN_MAP-Makro wird mit dem END_COLUMN_MAP-Makro abgeschlossen. Dieses Makro wird verwendet, wenn nur ein Accessor im Benutzerdatensatz erforderlich ist.

Spalten entsprechen den Feldern in dem Rowset, das Sie binden möchten.

#### <a name="example"></a>Beispiel

Hier sehen Sie ein Beispiel für eine Spalten- und Parameterzuordnung:

<!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->

### <a name="blob_entry"></a> BLOB_ENTRY

Mit BEGIN_COLUMN_MAP und END_COLUMN_MAP verwendet, um ein großes binäres Objekt zu binden ([BLOB](/previous-versions/windows/desktop/ms711511)).

#### <a name="syntax"></a>Syntax

```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)
```

#### <a name="parameters"></a>Parameter

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*IID*<br/>
[in] Schnittstellen-GUID, wie z. B. `IDD_ISequentialStream`verwendet, um das BLOB abrufen.

*flags*<br/>
[in] Vom OLE Structured Storage Modell definierte Speichermodus flags (z. B. `STGM_READ`).

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="example"></a>Beispiel

Finden Sie unter [wie kann ich einen BLOB abrufen?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_length"></a> BLOB_ENTRY_LENGTH

Mit BEGIN_COLUMN_MAP und END_COLUMN_MAP verwendet, um ein großes binäres Objekt zu binden ([BLOB](/previous-versions/windows/desktop/ms711511)). Ähnlich wie [BLOB_ENTRY](../../data/oledb/blob-entry.md), außer dass dieses Makro, auch über die Länge in Bytes der BLOB-Spalte erhält.

#### <a name="syntax"></a>Syntax

```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)
```

#### <a name="parameters"></a>Parameter

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*IID*<br/>
[in] Schnittstellen-GUID, wie z. B. `IDD_ISequentialStream`verwendet, um das BLOB abrufen.

*flags*<br/>
[in] Vom OLE Structured Storage Modell definierte Speichermodus flags (z. B. `STGM_READ`).

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[out] Die (tatsächlich) Länge in Bytes der BLOB-Spalte.

#### <a name="example"></a>Beispiel

Finden Sie unter [wie kann ich einen BLOB abrufen?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_length_status"></a> BLOB_ENTRY_LENGTH_STATUS

Mit BEGIN_COLUMN_MAP und END_COLUMN_MAP verwendet, um ein großes binäres Objekt zu binden ([BLOB](/previous-versions/windows/desktop/ms711511)). Ähnlich wie [BLOB_ENTRY](../../data/oledb/blob-entry.md), außer dass dieses Makro auch die Länge und den Status der BLOB-Spalte erhält.

#### <a name="syntax"></a>Syntax

```cpp
BLOB_ENTRY_LENGTH_STATUS(
    nOrdinal,
    IID,
    flags,
    data,
    length,
    status )
```

#### <a name="parameters"></a>Parameter

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*IID*<br/>
[in] Schnittstellen-GUID, wie z. B. `IDD_ISequentialStream`verwendet, um das BLOB abrufen.

*flags*<br/>
[in] Vom OLE Structured Storage Modell definierte Speichermodus flags (z. B. `STGM_READ`).

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[out] Die (tatsächlich) Länge in Bytes der BLOB-Spalte.

*Status*<br/>
[out] Der Status der BLOB-Spalte.

#### <a name="example"></a>Beispiel

Finden Sie unter [wie kann ich einen BLOB abrufen?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_entry_status"></a> BLOB_ENTRY_STATUS

BEGIN_COLUMN_MAP oder BEGIN_ACCESSOR_MAP verwendet werden, um ein großes binäres Objekt zu binden ([BLOB](/previous-versions/windows/desktop/ms711511)). Ähnlich wie [BLOB_ENTRY](../../data/oledb/blob-entry.md), außer dass dieses Makro auch den Status der BLOB-Spalte erhält.

#### <a name="syntax"></a>Syntax

```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)
```

#### <a name="parameters"></a>Parameter

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*IID*<br/>
[in] Schnittstellen-GUID, wie z. B. `IDD_ISequentialStream`verwendet, um das BLOB abrufen.

*flags*<br/>
[in] Vom OLE Structured Storage Modell definierte Speichermodus flags (z. B. `STGM_READ`).

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*Status*<br/>
[out] Der Status des BLOB-Felds.

#### <a name="example"></a>Beispiel

Finden Sie unter [wie kann ich einen BLOB abrufen?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_name"></a> BLOB_NAME

Mit BEGIN_COLUMN_MAP und END_COLUMN_MAP verwendet, um ein großes binäres Objekt zu binden ([BLOB](/previous-versions/windows/desktop/ms711511)). Ähnlich wie [BLOB_ENTRY](../../data/oledb/blob-entry.md), außer dass dieses Makro anstelle eine Spaltennummer des Namens einer Spalte verwendet.

#### <a name="syntax"></a>Syntax

```cpp
BLOB_NAME(pszName, IID, flags, data )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*IID*<br/>
[in] Schnittstellen-GUID, wie z. B. `IDD_ISequentialStream`verwendet, um das BLOB abrufen.

*flags*<br/>
[in] Vom OLE Structured Storage Modell definierte Speichermodus flags (z. B. `STGM_READ`).

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="example"></a>Beispiel

Finden Sie unter [wie kann ich einen BLOB abrufen?](../../data/oledb/retrieving-a-blob.md).

### <a name="blob_name_length"></a> BLOB_NAME_LENGTH

Mit BEGIN_COLUMN_MAP und END_COLUMN_MAP verwendet, um ein großes binäres Objekt zu binden ([BLOB](/previous-versions/windows/desktop/ms711511)). Ähnlich wie [BLOB_NAME](../../data/oledb/blob-name.md), außer dass dieses Makro, auch über die Länge in Bytes der BLOB-Spalte erhält.

#### <a name="syntax"></a>Syntax

```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*IID*<br/>
[in] Schnittstellen-GUID, wie z. B. `IDD_ISequentialStream`verwendet, um das BLOB abrufen.

*flags*<br/>
[in] Vom OLE Structured Storage Modell definierte Speichermodus flags (z. B. `STGM_READ`).

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[out] Die (tatsächlich) Länge in Bytes der BLOB-Spalte.

### <a name="blob_name_length_status"></a> BLOB_NAME_LENGTH_STATUS

Mit BEGIN_COLUMN_MAP und END_COLUMN_MAP verwendet, um ein großes binäres Objekt zu binden ([BLOB](/previous-versions/windows/desktop/ms711511)). Ähnlich wie [BLOB_NAME](../../data/oledb/blob-name.md), außer dass dieses Makro auch die Länge und den Status der BLOB-Spalte erhält.

#### <a name="syntax"></a>Syntax

```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length, status )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*IID*<br/>
[in] Schnittstellen-GUID, wie z. B. `IDD_ISequentialStream`verwendet, um das BLOB abrufen.

*flags*<br/>
[in] Vom OLE Structured Storage Modell definierte Speichermodus flags (z. B. `STGM_READ`).

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[out] Die (tatsächlich) Länge in Bytes der BLOB-Spalte.

*Status*<br/>
[out] Der Status des BLOB-Felds.

### <a name="blob_name_status"></a> BLOB_NAME_STATUS

Mit BEGIN_COLUMN_MAP und END_COLUMN_MAP verwendet, um ein großes binäres Objekt zu binden ([BLOB](/previous-versions/windows/desktop/ms711511)). Ähnlich wie [BLOB_NAME](../../data/oledb/blob-name.md), außer dass dieses Makro auch den Status der BLOB-Spalte erhält.

#### <a name="syntax"></a>Syntax

```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data, status )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*IID*<br/>
[in] Schnittstellen-GUID, wie z. B. `IDD_ISequentialStream`verwendet, um das BLOB abrufen.

*flags*<br/>
[in] Vom OLE Structured Storage Modell definierte Speichermodus flags (z. B. `STGM_READ`).

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*Status*<br/>
[out] Der Status des BLOB-Felds.

### <a name="bookmark_entry"></a> BOOKMARK_ENTRY

Bindet die Lesezeichenspalte an.

#### <a name="syntax"></a>Syntax

```cpp
BOOKMARK_ENTRY(variable)
```

#### <a name="parameters"></a>Parameter

*Variable*<br/>
[in] Die Variable an die Lesezeichenspalte gebunden werden muss.

#### <a name="example"></a>Beispiel

```cpp
class CArtistsBookmark
{
public:
// Data Elements
   CBookmark<4> m_bookmark;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

// Output binding map
BEGIN_COLUMN_MAP(CArtistsBookmark)
   BOOKMARK_ENTRY(m_bookmark)
   COLUMN_ENTRY(1, m_nAge)
   COLUMN_ENTRY(2, m_szFirstName)
   COLUMN_ENTRY(3, m_szLastName)
END_COLUMN_MAP()

   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_BOOKMARKS, true);
   }

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsBookmark, L" \
   SELECT \
      Age, \
      FirstName, \
      LastName \
      FROM Artists")
};
```

#### <a name="see-also"></a>Siehe auch

[CBookmark-Klasse](../../data/oledb/cbookmark-class.md)<br/>
[DBPROP_BOOKMARKS](/previous-versions/windows/desktop/ms709728)

### <a name="column_entry"></a> COLUMN_ENTRY

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY(nOrdinal, data)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845) in die *OLE DB-Programmierreferenz*.

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="remarks"></a>Hinweise

Das COLUMN_ENTRY-Makro wird in den folgenden Stellen verwendet:

- Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.

- Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.

- Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.

#### <a name="example"></a>Beispiel

Finden Sie unter den Beispielen in den Themen Makro [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).

### <a name="column_entry_ex"></a> COLUMN_ENTRY_EX

Stellt eine Bindung für das Rowset für die spezifische Spalte in der Datenbank dar.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845) in die *OLE DB-Programmierreferenz*.

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*wType*<br/>
[in] Der Datentyp.

*nLength*<br/>
[in] Die Datengröße in Bytes.

*nPrecision*<br/>
[in] Die maximale Genauigkeit verwenden, beim Abrufen von Daten und *wType* ist `DBTYPE_NUMERIC`. Andernfalls wird dieser Parameter ignoriert.

*nScale*<br/>
[in] Die Skalierung verwenden, beim Abrufen von Daten und *wType* ist `DBTYPE_NUMERIC` oder `DBTYPE_DECIMAL`.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[in] Die Variable an die Länge der Spalte gebunden werden muss.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

#### <a name="remarks"></a>Hinweise

Die COLUMN_ENTRY_EX-Marko wird in den folgenden Stellen verwendet:

- Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.

- Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.

- Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.

#### <a name="example"></a>Beispiel

Finden Sie unter [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="column_entry_length"></a> COLUMN_ENTRY_LENGTH

Stellt eine Bindung für das Rowset für die spezifische Spalte in der Datenbank dar.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845) in die *OLE DB-Programmierreferenz*.

*nOrdinal*<br/>
[in] Die Nummer der Spalte, beginnend bei eins. Lesezeichen entspricht Spalte 0 (null).

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[in] Die Variable an die Länge der Spalte gebunden werden muss.

#### <a name="remarks"></a>Hinweise

Dieses Makro unterstützt die *Länge* Variable. Es wird an folgenden Orten verwendet:

- Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.

- Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.

- Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.

### <a name="column_entry_length_status"></a> COLUMN_ENTRY_LENGTH_STATUS

Stellt eine Bindung für das Rowset für die spezifische Spalte in der Datenbank dar.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845) in die *OLE DB-Programmierreferenz*.

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[in] Die Variable an die Länge der Spalte gebunden werden muss.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

#### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro aus, wenn Sie Variablen für Länge und der Status unterstützen möchten. Es wird an folgenden Orten verwendet:

- Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.

- Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.

- Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.

### <a name="column_entry_ps"></a> COLUMN_ENTRY_PS

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY_PS(nOrdinal, nPrecision, nScale, data)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845) in die *OLE DB-Programmierreferenz*.

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*nPrecision*<br/>
[in] Die maximale Genauigkeit der Spalte, die Sie binden möchten.

*nScale*<br/>
[in] Die Dezimalstellen der Spalte, die Sie binden möchten.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="remarks"></a>Hinweise

Ermöglicht Ihnen die Angabe der Genauigkeit und Dezimalstellen der Spalte, die Sie binden möchten. Es wird an folgenden Orten verwendet:

- Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.

- Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.

- Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.

### <a name="column_entry_ps_length"></a> COLUMN_ENTRY_PS_LENGTH

Stellt eine Bindung für das Rowset für die spezifische Spalte in der Datenbank dar.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845) in die *OLE DB-Programmierreferenz*.

*nOrdinal*<br/>
[in] Die Nummer der Spalte, beginnend bei eins. Lesezeichen entspricht Spalte 0 (null).

*nPrecision*<br/>
[in] Die maximale Genauigkeit der Spalte, die Sie binden möchten.

*nScale*<br/>
[in] Die Dezimalstellen der Spalte, die Sie binden möchten.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[in] Die Variable an die Länge der Spalte gebunden werden muss.

#### <a name="remarks"></a>Hinweise

Ermöglicht Ihnen die Angabe der Genauigkeit und Dezimalstellen der Spalte, die Sie binden möchten. Dieses Makro unterstützt die *Länge* Variable. Es wird an folgenden Orten verwendet:

- Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.

- Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.

- Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.

### <a name="column_entry_ps_length_status"></a> COLUMN_ENTRY_PS_LENGTH_STATUS

Stellt eine Bindung für das Rowset für die spezifische Spalte in der Datenbank dar.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY_PS_LENGTH_STATUS(nOrdinal, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845) in die *OLE DB-Programmierreferenz*.

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*nPrecision*<br/>
[in] Die maximale Genauigkeit der Spalte, die Sie binden möchten.

*nScale*<br/>
[in] Die Dezimalstellen der Spalte, die Sie binden möchten.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[in] Die Variable an die Länge der Spalte gebunden werden muss.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

#### <a name="remarks"></a>Hinweise

Ermöglicht Ihnen die Angabe der Genauigkeit und Dezimalstellen der Spalte, die Sie binden möchten. Verwenden Sie dieses Makro aus, wenn Sie Variablen für Länge und der Status unterstützen möchten. Es wird an folgenden Orten verwendet:

- Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.

- Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.

- Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.

### <a name="column_entry_ps_status"></a> COLUMN_ENTRY_PS_STATUS

Stellt eine Bindung für das Rowset für die spezifische Spalte in der Datenbank dar.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845) in die *OLE DB-Programmierreferenz*.

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*nPrecision*<br/>
[in] Die maximale Genauigkeit der Spalte, die Sie binden möchten.

*nScale*<br/>
[in] Die Dezimalstellen der Spalte, die Sie binden möchten.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

#### <a name="remarks"></a>Hinweise

Ermöglicht Ihnen die Angabe der Genauigkeit und Dezimalstellen der Spalte, die Sie binden möchten. Dieses Makro unterstützt die *Status* Variable. Es wird an folgenden Orten verwendet:

- Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.

- Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.

- Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.

### <a name="column_entry_status"></a> COLUMN_ENTRY_STATUS

Stellt eine Bindung für das Rowset für die spezifische Spalte in der Datenbank dar.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)
```

#### <a name="parameters"></a>Parameter

Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845) in die *OLE DB-Programmierreferenz*.

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

#### <a name="remarks"></a>Hinweise

Dieses Makro unterstützt die *Status* Variable. Es wird an folgenden Orten verwendet:

- Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.

- Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.

- Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.

### <a name="column_entry_type"></a> COLUMN_ENTRY_TYPE

Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt *Typ* Parameter.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)
```

#### <a name="parameters"></a>Parameter

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*wType*<br/>
[in] Der Datentyp der Eintrag in der Spalte.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="remarks"></a>Hinweise

Dieses Makro ist eine spezielle Variante der [COLUMN_ENTRY](../../data/oledb/column-entry.md) Makro, das eine Möglichkeit zur Angabe des Datentyps enthält.

### <a name="column_entry_type_size"></a> COLUMN_ENTRY_TYPE_SIZE

Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt *Typ* und *Größe* Parameter.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)
```

#### <a name="parameters"></a>Parameter

*nOrdinal*<br/>
[in] Die Nummer der Spalte.

*wType*<br/>
[in] Der Datentyp der Eintrag in der Spalte.

*nLength*<br/>
[in] Die Größe der Eintrag in der Spalte in Bytes.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="remarks"></a>Hinweise

Dieses Makro ist eine spezielle Variante der [COLUMN_ENTRY](../../data/oledb/column-entry.md) Makro, das eine Möglichkeit zur Angabe der Größe der Daten und den Typ enthält.

### <a name="column_name"></a> SPALTENNAME

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_ENTRY](../../data/oledb/column-entry.md), außer dass dieses Makro anstelle die Nummer der Spalte den Namen der Spalte verwendet.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME(pszName, data)
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="remarks"></a>Hinweise

Die Makros COLUMN_NAME_ * dienen in denselben Situationen wie [COLUMN_ENTRY](../../data/oledb/column-entry.md):

- Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.

- Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.

- Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.

### <a name="column_name_ex"></a> COLUMN_NAME_EX

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro auch-Datentyp, Größe, Genauigkeit, Dezimalstellen, Länge der Spalte und Status in der Spalte verwendet.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*wType*<br/>
[in] Der Datentyp.

*nLength*<br/>
[in] Die Datengröße in Bytes.

*nPrecision*<br/>
[in] Die maximale Genauigkeit verwenden, beim Abrufen von Daten und *wType* ist `DBTYPE_NUMERIC`. Andernfalls wird dieser Parameter ignoriert.

*nScale*<br/>
[in] Die Skalierung verwenden, beim Abrufen von Daten und *wType* ist `DBTYPE_NUMERIC` oder `DBTYPE_DECIMAL`.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[in] Die Variable an die Länge der Spalte gebunden werden muss.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_length"></a> COLUMN_NAME_LENGTH

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro nutzt auch die Länge der Spalte.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_LENGTH(pszName, data, length)
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[in] Die Variable an die Länge der Spalte gebunden werden muss.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_length_status"></a> COLUMN_NAME_LENGTH_STATUS

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro nutzt auch die Länge der Spalte und der Spalte Status.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[in] Die Variable an die Länge der Spalte gebunden werden muss.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_ps"></a> COLUMN_NAME_PS

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro nutzt auch die Genauigkeit und Dezimalstellenanzahl.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_PS(pszName, nPrecision, nScale, data )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*nPrecision*<br/>
[in] Die maximale Genauigkeit der Spalte, die Sie binden möchten.

*nScale*<br/>
[in] Die Dezimalstellen der Spalte, die Sie binden möchten.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_ps_length"></a> COLUMN_NAME_PS_LENGTH

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro nutzt auch die Genauigkeit, Dezimalstellen und Spalte Länge.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_PS_LENGTH(pszName, nPrecision, nScale, data, length )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*nPrecision*<br/>
[in] Die maximale Genauigkeit der Spalte, die Sie binden möchten.

*nScale*<br/>
[in] Die Dezimalstellen der Spalte, die Sie binden möchten.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[in] Die Variable an die Länge der Spalte gebunden werden muss.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_ps_length_status"></a> COLUMN_NAME_PS_LENGTH_STATUS

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro nutzt auch die Genauigkeit, Dezimalstellen, Länge der Spalte und Status in der Spalte.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_PS_LENGTH_STATUS(pszName, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*nPrecision*<br/>
[in] Die maximale Genauigkeit der Spalte, die Sie binden möchten.

*nScale*<br/>
[in] Die Dezimalstellen der Spalte, die Sie binden möchten.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*length*<br/>
[in] Die Variable an die Länge der Spalte gebunden werden muss.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_ps_status"></a> COLUMN_NAME_PS_STATUS

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro nutzt auch die Genauigkeit, Dezimalstellen und Spalte Status.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_PS_STATUS(pszName, nPrecision, nScale, data, status )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*nPrecision*<br/>
[in] Die maximale Genauigkeit der Spalte, die Sie binden möchten.

*nScale*<br/>
[in] Die Dezimalstellen der Spalte, die Sie binden möchten.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_status"></a> COLUMN_NAME_STATUS

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro nutzt auch die Spalte Status.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_STATUS(pszName, data, status )
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_type"></a> COLUMN_NAME_TYPE

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro auch-Datentyp verwendet.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_TYPE(pszName, wType, data)
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*wType*<br/>
[in] Der Datentyp.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_type_ps"></a> COLUMN_NAME_TYPE_PS

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro auch-Datentyp, Genauigkeit und Dezimalstellen verwendet.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*wType*<br/>
[in] Der Datentyp.

*nPrecision*<br/>
[in] Die maximale Genauigkeit verwenden, beim Abrufen von Daten und *wType* ist `DBTYPE_NUMERIC`. Andernfalls wird dieser Parameter ignoriert.

*nScale*<br/>
[in] Die Skalierung verwenden, beim Abrufen von Daten und *wType* ist `DBTYPE_NUMERIC` oder `DBTYPE_DECIMAL`.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_type_size"></a> COLUMN_NAME_TYPE_SIZE

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro auch den Datentyp und Größe nutzt.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*wType*<br/>
[in] Der Datentyp.

*nLength*<br/>
[in] Die Datengröße in Bytes.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="column_name_type_status"></a> COLUMN_NAME_TYPE_STATUS

Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro nutzt auch die Data-Typ und der Spalte Status.

#### <a name="syntax"></a>Syntax

```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)
```

#### <a name="parameters"></a>Parameter

*pszName*<br/>
[in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies erreichen, indem eine "L" vor dem Namen, z. B. einfügen: `L"MyColumn"`.

*wType*<br/>
[in] Der Datentyp.

*Status*<br/>
[in] Die Variable auf den Status der Spalte gebunden werden soll.

*data*<br/>
[in] Der entsprechenden Datenmember im Benutzerdatensatz.

#### <a name="remarks"></a>Hinweise

Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen auf, wo die COLUMN_NAME_ *-Makros verwendet werden.

### <a name="end_column_map"></a> END_COLUMN_MAP

Markiert das Ende der Zuordnungseintrags-Spalte.

#### <a name="syntax"></a>Syntax

```cpp
END_COLUMN_MAP()
```

#### <a name="remarks"></a>Hinweise

Es wird mit einer einzelnen Accessors in einem Rowset verwendet. Das BEGIN_COLUMN_MAP-Makro wird mit dem END_COLUMN_MAP-Makro abgeschlossen.

#### <a name="example"></a>Beispiel

Finden Sie unter [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).

### <a name="define_command"></a> DEFINE_COMMAND

Gibt den Befehl, der verwendet wird, um das Rowset zu erstellen, bei Verwendung der [CCommand](../../data/oledb/ccommand-class.md) Klasse. Akzeptiert nur Zeichenfolgen-Datentypen, die Übereinstimmung des angegebenen Anwendungstyps (ANSI oder Unicode).

> [!NOTE]
>  Es wird empfohlen, die Verwendung von [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) statt DEFINE_COMMAND.

#### <a name="syntax"></a>Syntax

```cpp
DEFINE_COMMAND(x, szCommand)
```

#### <a name="parameters"></a>Parameter

*w*<br/>
[in] Der Name der Benutzerdatensatzklasse (Befehl).

*szCommand*<br/>
[in] Die Befehlszeichenfolge, die verwendet wird, um das Rowset zu erstellen, bei Verwendung [CCommand](../../data/oledb/ccommand-class.md).

#### <a name="remarks"></a>Hinweise

Die Befehlszeichenfolge, die Sie angeben, wird als Standard verwendet, wenn Sie keinen Befehlstext angeben der [CCommand:: Open](../../data/oledb/ccommand-open.md) Methode.

Dieses Makro akzeptiert ANSI-Zeichenfolgen, wenn es sich bei der Erstellung Ihrer Anwendung als ANSI oder Unicode-Zeichenfolgen, wenn Sie die Anwendung im Unicode-Format erstellen. Es wird empfohlen, die Verwendung von [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) statt DEFINE_COMMAND, da der erste Wert, Unicode-Zeichenfolgen, unabhängig von der Art der Anwendung ANSI- oder Unicode akzeptiert.

#### <a name="example"></a>Beispiel

Finden Sie unter [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="define_command_ex"></a> DEFINE_COMMAND_EX

Gibt den Befehl, der verwendet wird, um das Rowset zu erstellen, bei Verwendung der [CCommand](../../data/oledb/ccommand-class.md) Klasse. Unterstützt Unicode und ANSI-Anwendungen.

#### <a name="syntax"></a>Syntax

```cpp
DEFINE_COMMAND_EX(x, wszCommand)
```

#### <a name="parameters"></a>Parameter

*w*<br/>
[in] Der Name der Benutzerdatensatzklasse (Befehl).

*wszCommand*<br/>
[in] Die Befehlszeichenfolge, die verwendet wird, um das Rowset zu erstellen, bei Verwendung [CCommand](../../data/oledb/ccommand-class.md).

#### <a name="remarks"></a>Hinweise

Die Befehlszeichenfolge, die Sie angeben, wird als Standard verwendet, wenn Sie keinen Befehlstext angeben der [CCommand:: Open](../../data/oledb/ccommand-open.md) Methode.

Dieses Makro akzeptiert Unicode-Zeichenfolgen, unabhängig von der Art der Anwendung. Dieses Makro wird bevorzugt über [DEFINE_COMMAND](../../data/oledb/define-command.md) da Unicode unterstützt und ANSI-Anwendungen.

#### <a name="example"></a>Beispiel

Finden Sie unter [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).

### <a name="begin_param_map"></a> BEGIN_PARAM_MAP

Markiert den Beginn der Zuordnungseintrags-Parameter.

#### <a name="syntax"></a>Syntax

```cpp
BEGIN_PARAM_MAP(x)
```

#### <a name="parameters"></a>Parameter

*w*<br/>
[in] Der Name der Benutzerdatensatzklasse.

#### <a name="remarks"></a>Hinweise

Parameter werden verwendet, indem [Befehle](/previous-versions/windows/desktop/ms724608).

#### <a name="example"></a>Beispiel

Siehe das Beispiel für die [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) Makro.

### <a name="end_param_map"></a> END_PARAM_MAP

Markiert das Ende der Zuordnungseintrags-Parameter.

#### <a name="syntax"></a>Syntax

```cpp
END_PARAM_MAP()
```

#### <a name="example"></a>Beispiel

Siehe das Beispiel für die [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) Makro.

### <a name="set_param_type"></a> SET_PARAM_TYPE

Gibt an, COLUMN_ENTRY-Makros, die die SET_PARAM_TYPE-makroeingabe-, Ausgabe- oder Eingabe/Ausgabe folgen.

#### <a name="syntax"></a>Syntax

```cpp
SET_PARAM_TYPE(type)
```

#### <a name="parameters"></a>Parameter

*Typ*<br/>
[in] Der für den Parameter festzulegende Typ.

#### <a name="remarks"></a>Hinweise

Anbieter unterstützen nur Parametereingabe-/-ausgabetypen, die von der zugrunde liegenden Datenquelle unterstützt werden. Der Typ ist eine Kombination aus einem oder mehreren `DBPARAMIO` Werte (finden Sie unter [DBBINDING-Strukturen](/previous-versions/windows/desktop/ms716845) in die *OLE DB-Programmierreferenz*):

- `DBPARAMIO_NOTPARAM` Der Accessor hat keine Parameter. Legen Sie in der Regel `eParamIO` auf diesen Wert in zeilenaccessoren, um dem Benutzer daran zu erinnern, dass Parameter ignoriert werden.

- `DBPARAMIO_INPUT` Ein Eingabeparameter.

- `DBPARAMIO_OUTPUT` Ein Ausgabeparameter.

- `DBPARAMIO_INPUT | DBPARAMIO_OUTPUT` Der Parameter ist sowohl Eingabe-als auch ein Output-Parameter.

#### <a name="example"></a>Beispiel

```cpp
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
```

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Funktionen für OLE-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)