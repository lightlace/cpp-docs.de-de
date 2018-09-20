---
title: CDaoFieldInfo-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aaf3f41bf6a6fe5d67ec5835d57889f6ec7dbae6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437682"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo-Struktur

Die `CDaoFieldInfo` Struktur enthält Informationen über ein Field-Objekt, das für Datenzugriffsobjekte (DAO) definiert.

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
Eindeutig bezeichnet das Field-Objekt. Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

*m_nType*<br/>
Ein Wert, der den Datentyp des Felds angibt. Informationen finden Sie im Thema "Type-Eigenschaft" in-DAO-Hilfe. Der Wert dieser Eigenschaft kann einen der folgenden sein:

- `dbBoolean` Ja/Nein, identisch mit "true" / "false"

- `dbByte` Byte

- `dbInteger` kurze

- `dbLong` lange

- `dbCurrency` Währung; MFC-Klasse finden Sie unter [COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle` einzelne

- `dbDouble` Double-Wert

- `dbDate` Datum/Uhrzeit MFC-Klasse finden Sie unter [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText` Text MFC-Klasse finden Sie unter [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary` Long-Binärdatei (OLE-Objekt). Sie können die MFC-Klasse verwenden möchten [CByteArray](../../mfc/reference/cbytearray-class.md) statt Klasse `CLongBinary` als `CByteArray` ist umfangreicher und einfacher zu verwenden.

- `dbMemo` Gutschrift; finden Sie unter MFC-Klasse `CString`

- `dbGUID` Eine global eindeutige Bezeichner/Universally Unique Identifier mit Remoteprozeduraufrufen verwendet. Weitere Informationen finden Sie im Thema "Type-Eigenschaft" in-DAO-Hilfe.

> [!NOTE]
>  Verwenden Sie nicht den String-Datentypen, für binäre Daten. Dies bewirkt, dass Ihre Daten durch die Unicode/ANSI-Übersetzungsschicht, was zu höheren Verwaltungsaufwand und möglicherweise unerwartete Übersetzung zu übergeben.

*m_lSize*<br/>
Ein Wert, der die maximale Größe in Bytes ein DAO-Field-Objekt gibt an, die Text enthält die feste Größe von einem Feldobjekt, das Text oder numerische Werte enthält. Informationen finden Sie im Thema "Size-Eigenschaft" in-DAO-Hilfe. Größen der folgenden Werte sind möglich:

|Typ|Größe (Byte)|Beschreibung|
|----------|--------------------|-----------------|
|`dbBoolean`|1 Byte|Ja/Nein (identisch mit WAHR/FALSCH)|
|`dbByte`|1|Byte|
|`dbInteger`|2|Ganze Zahl|
|`dbLong`|4|Long|
|`dbCurrency`|8|Währung ([COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Single|
|`dbDouble`|8|Double|
|`dbDate`|8|Datum/Uhrzeit ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Text ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long-Binärdatei (OLE-Objekt; [CByteArray](../../mfc/reference/cbytearray-class.md); verwenden Sie anstelle von `CLongBinary`)|
|`dbMemo`|0|Memo ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|Eine global eindeutige Bezeichner/Universally Unique Identifier mit Remoteprozeduraufrufen verwendet.|

*m_lAttributes*<br/>
Gibt die Eigenschaften des ein Field-Objekt, das eine Tabledef Recordset, Querydef oder Index-Objekt enthalten sind. Der zurückgegebene Wert kann eine Summe der folgenden Konstanten, erstellt mit dem C++-, bitweise OR-sein (**&#124;**) Operator:

- `dbFixedField` Die Größe des Felds ist (Standard für numerische Felder) behoben.

- `dbVariableField` Die Größe des Felds ist die Variable (gilt nur für Text-Felder).

- `dbAutoIncrField` Der Feldwert für neue Datensätze wird auf eine eindeutige lange Ganzzahl, die nicht geändert werden kann, automatisch erhöht. Nur unterstützt für Microsoft Jet-Datenbank-Tabellen.

- `dbUpdatableField` Der Wert des Felds kann geändert werden.

- `dbDescending` Das Feld wird sortiert in absteigender (Z – A oder 0, 100) Reihenfolge (gilt nur für eine Field-Objekt in einer Fields-Auflistung eines Index-Objekts; in MFC, Index-Objekte sind selbst in Tabledef-Objekte enthalten). Wenn Sie diese Konstante weglassen, wird das Feld in aufsteigender sortiert (A – Z oder 0 - 100) Reihenfolge (Standard).

Wenn Sie die Einstellung dieser Eigenschaft zu überprüfen, können Sie die C++ bitweise- und Operator (**&**) für ein bestimmtes Attribut zu testen. Wenn Sie mehrere Attribute festlegen möchten, können Sie Sie kombinieren, durch die entsprechenden Konstanten mit dem bitweisen OR-Kombination (**&#124;**) Operator. Informationen finden Sie im Thema "Attributes-Eigenschaft" in-DAO-Hilfe.

*m_nOrdinalPosition*<br/>
Ein Wert, der die numerische Reihenfolge angibt, in der ein Feld, das von einem DAO-Feld-Objekt dargestellt wird, relativ zu anderen Feldern angezeigt werden soll. Sie können diese Eigenschaft festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield). Informationen finden Sie im Thema "OrdinalPosition-Eigenschaft" in-DAO-Hilfe.

*m_bRequired*<br/>
Gibt an, ob ein DAO-Field-Objekt einen Wert ungleich Null erfordert. Wenn diese Eigenschaft auf "true" ist, lässt das Feld keinen Null-Wert. Bei Bedarf auf "FALSE" festgelegt ist das Feld darf Null-Werte sowie Werte, die die leere Zeichenfolge und ValidationRule eigenschafteneinstellungen angegebenen Bedingungen erfüllen. Weitere Informationen finden Sie unter dem Thema "Erforderliche Eigenschaft" in-DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_bAllowZeroLength*<br/>
Gibt an, ob eine leere Zeichenfolge ("") ist ein gültiger Wert von einem DAO-Field-Objekt mit einem Text- oder Memo-Datentyp. Wenn diese Eigenschaft auf "true" ist, ist eine leere Zeichenfolge ein gültiger Wert. Sie können diese Eigenschaft festlegen, auf "false", um sicherzustellen, dass Sie eine leere Zeichenfolge verwenden können, um den Wert eines Felds festzulegen. Weitere Informationen finden Sie unter dem Thema "Leere Zeichenfolge-Eigenschaft" in-DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_lCollatingOrder*<br/>
Gibt die Sequenz der Sortierreihenfolge im Text für den Zeichenfolgenvergleich oder sortieren. Weitere Informationen finden Sie unter dem Thema "Anpassen von Windows-Registrierung Einstellungen für den Datenzugriff" in-DAO-Hilfe. Eine Liste der möglichen Werte zurückgegeben werden soll, finden Sie unter den `m_lCollatingOrder` Mitglied der [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) Struktur. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strForeignName*<br/>
Ein Wert, der Teil einer Beziehung, den Namen des Objekts die DAO-Feld in einer Fremdschlüsseltabelle gibt an, die ein Feld in einer primären Tabelle entspricht. Informationen finden Sie im Thema "ForeignName-Eigenschaft" in-DAO-Hilfe.

*m_strSourceField*<br/>
Gibt den Namen des Felds, das die ursprüngliche Quelle der Daten für ein DAO-Field-Objekt ein Tabledef, Recordset oder Querydef-Objekt enthalten ist. Diese Eigenschaft gibt den ursprünglichen Feldnamen ein Field-Objekt zugeordnet. Beispielsweise können Sie diese Eigenschaft verwenden, um die ursprüngliche Quelle der Daten in einem Abfragefeld zu ermitteln, deren Name nicht mit den Namen des Felds in der zugrunde liegenden Tabelle verknüpft ist. Informationen finden Sie im Thema "SourceField, SourceTable-Eigenschaften" in-DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strSourceTable*<br/>
Gibt den Namen der Tabelle, die die ursprüngliche Quelle der Daten für ein DAO-Field-Objekt ein Tabledef, Recordset oder Querydef-Objekt enthalten ist. Diese Eigenschaft gibt den ursprünglichen Tabellennamen ein Field-Objekt zugeordnet. Beispielsweise können Sie diese Eigenschaft verwenden, um die ursprüngliche Quelle der Daten in einem Abfragefeld zu ermitteln, deren Name nicht mit den Namen des Felds in der zugrunde liegenden Tabelle verknüpft ist. Informationen finden Sie im Thema "SourceField, SourceTable-Eigenschaften" in-DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strValidationRule*<br/>
Ein Wert, der die Daten in einem Feld überprüft werden, da sie geändert oder einer Tabelle hinzugefügt. Informationen finden Sie im Thema "ValidationRule-Eigenschaft" in-DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

Weitere Informationen zu Tabledefs finden Sie unter den `m_strValidationRule` Mitglied der [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) Struktur.

*m_strValidationText*<br/>
Ein Wert, der den Text der Nachricht, die Ihre Anwendung angezeigt angibt, wenn der Wert eines Objekts der DAO-Feld die Validierungsregel gemäß der ValidationRule-Eigenschaft nicht erfüllt. Informationen finden Sie im Thema "ValidationText-Eigenschaft" in-DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strDefaultValue*<br/>
Der Standardwert eines DAO-Feld-Objekts. Wenn ein neuer Datensatz erstellt wird, wird die Einstellung der DefaultValue-Eigenschaft automatisch als der Wert für das Feld eingegeben. Weitere Informationen finden Sie unter dem Thema "DefaultValue-Eigenschaft" in-DAO-Hilfe. Sie können diese Eigenschaft für eine Tabledef mit festlegen [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

## <a name="remarks"></a>Hinweise

Die Verweise auf die primäre, sekundäre und alle oben angegeben, wie die Informationen zurückgegeben werden, indem die `GetFieldInfo` Memberfunktion in Klassen [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), und [ CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).

Field-Objekte werden nicht durch eine MFC-Klasse dargestellt. Stattdessen die DAO-Objekte, die zugrunde liegende MFC-Objekten, die folgenden Klassen enthalten Auflistungen von Feld-Objekten: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), und [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Diese Klassen geben Member-Funktionen für den Zugriff auf einige Elemente Feldinformationen an, oder darauf gleichzeitig mit zugreifen eine `CDaoFieldInfo` -Objekt durch Aufrufen der `GetFieldInfo` Memberfunktion Rand des enthaltenden Objekts.

Neben dem deren Verwendung zum Untersuchen von Objekteigenschaften können Sie auch `CDaoFieldInfo` um einen Eingabeparameter für das Erstellen neuer Felder in einer Tabledef zu erstellen. Für diese Aufgabe einfachere Optionen zur Verfügung, aber wenn Sie eine präzisere Kontrolle wünschen, können Sie die Version des [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) , akzeptiert eine `CDaoFieldInfo` Parameter.

Informationen, die abgerufen, indem die `GetFieldInfo` Member-Funktion (der Klasse, die das Feld enthält) befindet sich in einem `CDaoFieldInfo` Struktur. Rufen Sie die `GetFieldInfo` Memberfunktion Rand des enthaltenden Objekts in die Auflistung, deren Felder der Field-Objekt gespeichert wird. `CDaoFieldInfo` definiert auch eine `Dump` -Memberfunktion im Debug-builds. Können Sie `Dump` zum Sichern den Inhalt einer `CDaoFieldInfo` Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)

