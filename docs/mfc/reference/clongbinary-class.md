---
title: CLongBinary-Klasse
ms.date: 11/04/2016
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
helpviewer_keywords:
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
ms.openlocfilehash: a7dbb7e38ec01743d994dafd6c7945e306de51ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656035"
---
# <a name="clongbinary-class"></a>CLongBinary-Klasse

Vereinfacht die Verwendung sehr großen Binärdatenobjekte (oft "BLOBs" oder "Binary Large Objects" genannt) in einer Datenbank.

## <a name="syntax"></a>Syntax

```
class CLongBinary : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CLongBinary::CLongBinary](#clongbinary)|Erstellt ein `CLongBinary`-Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Enthält die tatsächliche Größe in Bytes des-Objekts, dessen Handle sich in befindet `m_hData`.|
|[CLongBinary::m_hData](#m_hdata)|Enthält ein Windows-HGLOBAL-Handle für das eigentliche Bild-Objekt.|

## <a name="remarks"></a>Hinweise

Beispielsweise kann ein Datensatzfeld im SQL-Tabelle eine Bitmap, ein Bild darstellt enthalten. Ein `CLongBinary` Objekt speichert ein solches Objekt und verfolgt seine Größe.

> [!NOTE]
>  Im Allgemeinen ist es jetzt empfehlenswert, verwenden Sie [CByteArray](../../mfc/reference/cbytearray-class.md) in Verbindung mit der [DFX_Binary](record-field-exchange-functions.md#dfx_binary) Funktion. Sie können weiterhin verwenden `CLongBinary`, aber im allgemeinen `CByteArray` bietet mehr Funktionen unter Win32, da es nicht mehr ist die größenbeschränkung mit 16-Bit-gefunden `CByteArray`. Diese Empfehlung gilt für die Programmierung mit Datenzugriffsobjekte (DAO) als auch für Open Database Connectivity (ODBC).

Verwenden einer `CLongBinary` Objekt deklarieren Sie einen Felddatenmember vom Typ `CLongBinary` im Recordset-Klasse. Dieses Element wird ein eingebettetes Element der Recordset-Klasse und wird erstellt werden, wenn das Recordset erstellt wird. Nach der `CLongBinary` -Objekt erstellt wird und die Datensatzfeldaustausch (RFX)-Mechanismus das Datenobjekt, das aus einem Feld im aktuellen Datensatz in der Datenquelle geladen, und speichert sie wieder auf den Eintrag, wenn der Datensatz aktualisiert wird. RFX fragt die Datenquelle aus, für die Größe der binary large Object, Speicher zuweist, dafür (über die `CLongBinary` des Objekts `m_hData` Datenmember), und speichert eine `HGLOBAL` handle für die Daten in `m_hData`. RFX speichert auch die tatsächliche Größe des Objekts in der `m_dwDataLength` -Datenmember. Arbeiten mit den Daten in das Objekt über `m_hData`, mit den gleichen Verfahren, die normalerweise würden Sie verwenden zum Bearbeiten der Daten, die in einer Windows `HGLOBAL` behandeln.

Wenn Sie das Recordset, das eingebettete zerstören `CLongBinary` auch-Objekt zerstört wird und dessen Destruktor hebt die Zuordnung der `HGLOBAL` Daten Handle.

Weitere Informationen zu großen Objekten und die Verwendung von `CLongBinary`, finden Sie in den Artikeln [Recordsets (ODBC)](../../data/odbc/recordset-odbc.md) und [Recordset: Arbeiten mit großen von Elementen (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>Anforderungen

**Header:** afxdb_.h

##  <a name="clongbinary"></a>  CLongBinary::CLongBinary

Erstellt ein `CLongBinary`-Objekt.

```
CLongBinary();
```

##  <a name="m_dwdatalength"></a>  CLongBinary::m_dwDataLength

Speichert die tatsächliche Größe in Bytes, der die Daten im HGLOBAL Handles in `m_hData`.

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>Hinweise

Diese Größe möglicherweise kleiner als die Größe des Speicherblocks, der für die Daten. Rufen Sie die Win32 [GlobalSize ist](/windows/desktop/api/winbase/nf-winbase-globalsize) Funktion, um die zugeordnete Größe abzurufen.

##  <a name="m_hdata"></a>  CLongBinary::m_hData

Speichert ein HGLOBAL für Windows-Handle für die tatsächliche binary large Object-Daten.

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)
