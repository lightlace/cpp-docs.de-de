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
ms.openlocfilehash: 94666c0d15898e05ae78663a15d86b7d00d5c9c6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505670"
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
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Enthält die tatsächliche Größe des Datenobjekts in Bytes, dessen Handle in `m_hData`gespeichert wird.|
|[CLongBinary::m_hData](#m_hdata)|Enthält ein Windows-HGLOBAL-Handle für das eigentliche Image-Objekt.|

## <a name="remarks"></a>Hinweise

Beispielsweise kann ein Daten Satz Feld in einer SQL-Tabelle eine Bitmap enthalten, die ein Bild darstellt. Ein `CLongBinary` -Objekt speichert ein solches Objekt und verfolgt seine Größe.

> [!NOTE]
>  Im Allgemeinen ist es jetzt besser, [CByteArray](../../mfc/reference/cbytearray-class.md) in Verbindung mit der [DFX_Binary](record-field-exchange-functions.md#dfx_binary) -Funktion zu verwenden. Sie können weiterhin verwenden `CLongBinary`, aber im allgemeinen `CByteArray` werden unter Win32 weitere Funktionen bereitstellen, da die Größenbeschränkung mit 16-Bit `CByteArray`-Werten nicht länger auftritt. Diese Empfehlung gilt für die Programmierung mit Data Access Objects (DAO) und Open Database Connectivity (ODBC).

Um ein `CLongBinary` -Objekt zu verwenden, deklarieren Sie einen Felddatenmember vom Typ `CLongBinary` in der Recordset-Klasse. Dieser Member ist ein eingebettetes Element der Recordset-Klasse und wird beim Konstruieren des Recordsets erstellt. Nachdem das `CLongBinary` Objekt erstellt wurde, lädt der Mechanismus für den Daten Satz Feld Austausch (RFX) das Datenobjekt aus einem Feld im aktuellen Datensatz in der Datenquelle und speichert es wieder im Datensatz, wenn der Datensatz aktualisiert wird. RFX fragt die Datenquelle nach der Größe des Binary Large Object ab, ordnet ihr Speicher `CLongBinary` zu (über das `m_hData` Datenmember des Objekts) und speichert ein `HGLOBAL` Handle für die Daten in `m_hData`. RFX speichert außerdem die tatsächliche Größe des Datenobjekts im `m_dwDataLength` Datenmember. Arbeiten Sie mit den Daten im-Objekt `m_hData`mithilfe derselben Techniken, die Sie normalerweise verwenden würden, um die in einem Windows `HGLOBAL` -handle gespeicherten Daten zu bearbeiten.

Wenn Sie das Recordset zerstören, wird das `CLongBinary` eingebettete Objekt ebenfalls zerstört, und der Dekonstruktor hebt die `HGLOBAL` Zuordnung des Daten Handles auf.

Weitere Informationen zu großen Objekten und zur Verwendung von finden `CLongBinary`Sie in den Artikeln [Recordset (ODBC)](../../data/odbc/recordset-odbc.md) und [Recordset: Arbeiten mit großen Datenelementen (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>Anforderungen

**Header:** afxdb_. h

##  <a name="clongbinary"></a>CLongBinary:: CLongBinary

Erstellt ein `CLongBinary`-Objekt.

```
CLongBinary();
```

##  <a name="m_dwdatalength"></a>CLongBinary:: m_dwDataLength

Speichert die tatsächliche Größe der Daten in Bytes, die im HGLOBAL-Handle in `m_hData`gespeichert sind.

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>Hinweise

Diese Größe kann kleiner sein als die Größe des für die Daten zugewiesenen Speicherblocks. Zum Abrufen der zugeordneten Größe können Sie die Win32 [Global size](/windows/win32/api/winbase/nf-winbase-globalsize) -Funktion abrufen.

##  <a name="m_hdata"></a>CLongBinary:: m_hData

Speichert ein Windows-HGLOBAL-Handle für die tatsächlichen Binary Large Object Daten.

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)
