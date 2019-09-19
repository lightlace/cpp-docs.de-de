---
title: CDaoFieldInfo-Struktur
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: e98f5ba69f6702dd768cfe6605f993064e1b896c
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096102"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo-Struktur

Die `CDaoFieldInfo` Struktur enthält Informationen über ein für Data Access Objects (DAO) definiertes Feld Objekt.

DAO wird über Office 2013 unterstützt. DAO 3,6 ist die endgültige Version und wird als veraltet eingestuft.

## <a name="syntax"></a>Syntax

```
struct CDaoFieldInfo
{
    CString m_strName;           // Primary
    short m_nType;               // Primary
    long m_lSize;                // Primary
    long m_lAttributes;          // Primary
    short m_nOrdinalPosition;    // Secondary
    BOOL m_bRequired;            // Secondary
    BOOL m_bAllowZeroLength;     // Secondary
    long m_lCollatingOrder;      // Secondary
    CString m_strForeignName;    // Secondary
    CString m_strSourceField;    // Secondary
    CString m_strSourceTable;    // Secondary
    CString m_strValidationRule; // All
    CString m_strValidationText; // All
    CString m_strDefaultValue;   // All
};
```

#### <a name="parameters"></a>Parameter

*m_strName*<br/>
Benennt das Feld Objekt eindeutig. Weitere Informationen finden Sie im Thema "Name Property" in der DAO-Hilfe.

*m_nType*<br/>
Ein-Wert, der den Datentyp des Felds angibt. Weitere Informationen finden Sie im Thema "Type Property" in der DAO-Hilfe. Der Wert dieser Eigenschaft kann einer der folgenden Werte sein:

- `dbBoolean`Ja/Nein, identisch mit true/false

- `dbByte`Hobby

- `dbInteger`Kurzem

- `dbLong`Lange

- `dbCurrency`Währungs Weitere Informationen finden Sie unter MFC-Klasse [COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle`Gänger

- `dbDouble`Maß

- `dbDate`Datum/Uhrzeit; Siehe MFC-Klasse [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText`Text Siehe MFC-Klasse [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary`Long Binary (OLE-Objekt); Möglicherweise möchten Sie die MFC-Klasse " [CByteArray](../../mfc/reference/cbytearray-class.md) " `CLongBinary` anstelle `CByteArray` von "Class" verwenden, da umfangreicher und einfacher zu verwenden ist.

- `dbMemo`Anruf Siehe MFC-Klasse`CString`

- `dbGUID`Einen global eindeutigen Bezeichner/universell eindeutigen Bezeichner, der mit Remote Prozedur aufrufen verwendet wird. Weitere Informationen finden Sie im Thema "Type Property" in der DAO-Hilfe.

> [!NOTE]
>  Verwenden Sie keine Zeichen folgen-Datentypen für Binärdaten. Dies bewirkt, dass Ihre Daten die Unicode/ANSI-Übersetzungs Schicht passieren, wodurch mehr Aufwand und möglicherweise unerwartete Übersetzungen entstehen.

*m_lSize*<br/>
Ein Wert, der die maximale Größe eines DAO-Feld Objekts in Bytes angibt, das Text oder die festgelegte Größe eines Feld Objekts enthält, das Text-oder numerische Werte enthält. Weitere Informationen finden Sie im Thema "Size-Eigenschaft" in der DAO-Hilfe. Die Größe kann einen der folgenden Werte aufweisen:

|Typ|Größe (Byte)|Beschreibung|
|----------|--------------------|-----------------|
|`dbBoolean`|1 Byte|Ja/Nein (identisch mit true/false)|
|`dbByte`|1|Byte|
|`dbInteger`|2|Ganze Zahl|
|`dbLong`|4|Long|
|`dbCurrency`|8|Währung ([COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Single|
|`dbDouble`|8|Double|
|`dbDate`|8|Datum/Uhrzeit ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Text ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long Binary (OLE-Objekt; [CByteArray](../../mfc/reference/cbytearray-class.md); Verwenden Sie anstelle `CLongBinary`von)|
|`dbMemo`|0|Memo ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|Einen global eindeutigen Bezeichner/universell eindeutigen Bezeichner, der mit Remote Prozedur aufrufen verwendet wird.|

*m_lAttributes*<br/>
Gibt Merkmale eines Feld Objekts an, das in einem Tabledef-, Recordset-, QueryDef-oder Index-Objekt enthalten ist. Der zurückgegebene Wert kann eine Summe dieser Konstanten sein, die mit dem C++ bitweisen OR-Operator ( **&#124;** ) erstellt wird:

- `dbFixedField`Die Feldgröße ist Fixed (Standardwert für numerische Felder).

- `dbVariableField`Die Feldgröße ist variabel (nur Text Felder).

- `dbAutoIncrField`Der Feldwert für neue Datensätze wird automatisch zu einer eindeutigen langen Ganzzahl erhöht, die nicht geändert werden kann. Wird nur für Microsoft Jet-Datenbanktabellen unterstützt.

- `dbUpdatableField`Der Feldwert kann geändert werden.

- `dbDescending`Das Feld wird in absteigender Reihenfolge (Z-A oder 100-0) sortiert (gilt nur für ein Feld Objekt in einer Fields-Auflistung eines Index Objekts; in MFC sind Index Objekte selbst in Tabledef-Objekten enthalten). Wenn Sie diese Konstante weglassen, wird das Feld in aufsteigender Reihenfolge (A-Z oder 0-100) sortiert (Standard).

Wenn Sie die Einstellung dieser Eigenschaft überprüfen, können Sie den C++ bitweisen AND-Operator ( **&** ) verwenden, um auf ein bestimmtes Attribut zu testen. Beim Festlegen mehrerer Attribute können Sie diese kombinieren, indem Sie die entsprechenden Konstanten mit dem bitweisen or ( **&#124;** )-Operator kombinieren. Weitere Informationen finden Sie im Thema "Attribute-Eigenschaft" in der DAO-Hilfe.

*m_nOrdinalPosition*<br/>
Ein-Wert, der die numerische Reihenfolge angibt, in der ein von einem DAO-Feld Objekt dargestelltes Feld relativ zu anderen Feldern angezeigt werden soll. Sie können diese Eigenschaft mit " [CDaoTableDef:: kreatefield](../../mfc/reference/cdaotabledef-class.md#createfield)" festlegen. Weitere Informationen finden Sie im Thema "Ordinalposition-Eigenschaft" in der DAO-Hilfe.

*m_bRequired*<br/>
Gibt an, ob ein DAO-Feld Objekt einen nicht-NULL-Wert erfordert. Wenn diese Eigenschaft true ist, lässt das Feld keinen NULL-Wert zu. Wenn erforderlich auf false festgelegt ist, kann das Feld NULL-Werte sowie Werte enthalten, die die durch die Eigenschaften Einstellungen AllowZeroLength und ValidationRule angegebenen Bedingungen erfüllen. Weitere Informationen finden Sie im Thema "erforderliche Eigenschaft" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef-Eigenschaft mit [CDaoTableDef:: kreatefield](../../mfc/reference/cdaotabledef-class.md#createfield)festlegen.

*m_bAllowZeroLength*<br/>
Gibt an, ob eine leere Zeichenfolge ("") ein gültiger Wert eines DAO-Feld Objekts mit einem Text-oder Memo-Datentyp ist. Wenn diese Eigenschaft den Wert true hat, ist eine leere Zeichenfolge ein gültiger-Wert. Sie können diese Eigenschaft auf false festlegen, um sicherzustellen, dass Sie keine leere Zeichenfolge verwenden können, um den Wert eines Felds festzulegen. Weitere Informationen finden Sie im Thema "AllowZeroLength Property" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef-Eigenschaft mit [CDaoTableDef:: kreatefield](../../mfc/reference/cdaotabledef-class.md#createfield)festlegen.

*m_lCollatingOrder*<br/>
Gibt die Reihenfolge der Sortierreihenfolge im Text für den Zeichen folgen Vergleich oder die Sortierung an. Weitere Informationen finden Sie im Thema zum Anpassen der Windows-Registrierungs Einstellungen für den Datenzugriff in der DAO-Hilfe. Eine Liste der möglichen Werte, die zurückgegeben werden, `m_lCollatingOrder` finden Sie unter dem-Member der [cdaodatabaseingefo](../../mfc/reference/cdaodatabaseinfo-structure.md) -Struktur. Sie können diese Eigenschaft für eine Tabledef-Eigenschaft mit [CDaoTableDef:: kreatefield](../../mfc/reference/cdaotabledef-class.md#createfield)festlegen.

*m_strForeignName*<br/>
Ein-Wert, der in einer Beziehung den Namen des DAO-Feld Objekts in einer fremd Tabelle angibt, das einem Feld in einer primären Tabelle entspricht. Weitere Informationen finden Sie im Thema "Ausländer Name-Eigenschaft" in der DAO-Hilfe.

*m_strSourceField*<br/>
Gibt den Namen des Felds an, das die ursprüngliche Quelle der Daten für ein DAO-Feld Objekt ist, das in einem Tabledef-, Recordset-oder QueryDef-Objekt enthalten ist. Diese Eigenschaft gibt den ursprünglichen Feldnamen an, der einem Feld Objekt zugeordnet ist. Beispielsweise können Sie diese Eigenschaft verwenden, um die ursprüngliche Quelle der Daten in einem Abfragefeld zu bestimmen, deren Name nicht mit dem Namen des Felds in der zugrunde liegenden Tabelle verknüpft ist. Weitere Informationen finden Sie im Thema "SourceField, SourceTable Properties" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef-Eigenschaft mit [CDaoTableDef:: kreatefield](../../mfc/reference/cdaotabledef-class.md#createfield)festlegen.

*m_strSourceTable*<br/>
Gibt den Namen der Tabelle an, die die ursprüngliche Quelle der Daten für ein DAO-Feld Objekt ist, das in einem Tabledef-, Recordset-oder QueryDef-Objekt enthalten ist. Diese Eigenschaft gibt den ursprünglichen Tabellennamen an, der einem Feld Objekt zugeordnet ist. Beispielsweise können Sie diese Eigenschaft verwenden, um die ursprüngliche Quelle der Daten in einem Abfragefeld zu bestimmen, deren Name nicht mit dem Namen des Felds in der zugrunde liegenden Tabelle verknüpft ist. Weitere Informationen finden Sie im Thema "SourceField, SourceTable Properties" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef-Eigenschaft mit [CDaoTableDef:: kreatefield](../../mfc/reference/cdaotabledef-class.md#createfield)festlegen.

*m_strValidationRule*<br/>
Ein Wert, der die Daten in einem Feld überprüft, wenn es geändert oder einer Tabelle hinzugefügt wird. Weitere Informationen finden Sie im Thema "ValidationRule Property" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef-Eigenschaft mit [CDaoTableDef:: kreatefield](../../mfc/reference/cdaotabledef-class.md#createfield)festlegen.

Weitere Informationen zu Tabledefs finden Sie unter dem `m_strValidationRule` -Member der [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) -Struktur.

*m_strValidationText*<br/>
Ein-Wert, der den Text der Meldung angibt, die von der Anwendung angezeigt wird, wenn der Wert eines DAO-Feld Objekts nicht der Validierungs Regel entspricht, die durch die ValidationRule-Eigenschafts Einstellung angegeben wird. Weitere Informationen finden Sie im Thema "ValidationText Property" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef-Eigenschaft mit [CDaoTableDef:: kreatefield](../../mfc/reference/cdaotabledef-class.md#createfield)festlegen.

*m_strDefaultValue*<br/>
Der Standardwert eines DAO-Feld Objekts. Wenn ein neuer Datensatz erstellt wird, wird die Einstellung der DefaultValue-Eigenschaft automatisch als Wert für das Feld eingegeben. Weitere Informationen finden Sie im Thema "DefaultValue-Eigenschaft" in der DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef-Eigenschaft mit [CDaoTableDef:: kreatefield](../../mfc/reference/cdaotabledef-class.md#createfield)festlegen.

## <a name="remarks"></a>Hinweise

Die Verweise auf Primary, Secondary und all oberhalb geben an, wie `GetFieldInfo` die Informationen von der Member-Funktion in den Klassen [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)zurückgegeben werden.

Feld Objekte werden nicht durch eine MFC-Klasse dargestellt. Stattdessen enthalten die DAO-Objekte, die zugrunde liegenden MFC-Objekten der folgenden Klassen sind, Auflistungen von Feld Objekten: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)und [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Diese Klassen stellen Element Funktionen bereit, um auf einige einzelne Elemente von Feldinformationen zuzugreifen, oder Sie können alle auf einmal mit `CDaoFieldInfo` einem-Objekt aufrufen `GetFieldInfo` , indem Sie die-Member-Funktion des enthaltenden Objekts aufrufen.

Neben der Verwendung zum Untersuchen von Objekteigenschaften können Sie auch `CDaoFieldInfo` verwenden, um einen Eingabeparameter zum Erstellen neuer Felder in einer Tabledef zu erstellen. Für diese Aufgabe sind einfachere Optionen verfügbar. Wenn Sie jedoch eine präzisere Kontrolle wünschen, können Sie die-Version von [CDaoTableDef:: kreatefield](../../mfc/reference/cdaotabledef-class.md#createfield) verwenden `CDaoFieldInfo` , die einen-Parameter annimmt.

Die von der `GetFieldInfo` -Element Funktion (der-Klasse, die das Feld enthält) abgerufenen Informationen `CDaoFieldInfo` werden in einer-Struktur gespeichert. Ruft die `GetFieldInfo` Member-Funktion des enthaltenden Objekts in auf, dessen Fields-Auflistung das Feld Objekt speichert. `CDaoFieldInfo`definiert auch eine `Dump` Member-Funktion in Debugbuilds. Sie können verwenden `Dump` , um den Inhalt `CDaoFieldInfo` eines-Objekts zu speichern.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
