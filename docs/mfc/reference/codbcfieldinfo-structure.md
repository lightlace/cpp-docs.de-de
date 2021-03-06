---
title: CODBCFieldInfo-Struktur
ms.date: 11/04/2016
f1_keywords:
- CODBCFieldInfo
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
ms.openlocfilehash: bc2ad0c8319a60b773211dbd6b52b57bb2dbcafb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388190"
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo-Struktur

Die `CODBCFieldInfo` Struktur enthält Informationen zu den Feldern in einer ODBC-Datenquelle.

## <a name="syntax"></a>Syntax

```
struct CODBCFieldInfo
{
    CString m_strName;
    SWORD m_nSQLType;
    UDWORD m_nPrecision;
    SWORD m_nScale;
    SWORD m_nNullability;
};
```

#### <a name="parameters"></a>Parameter

*m_strName*<br/>
Der Name des Felds.

*m_nSQLType*<br/>
Der SQL-Datentyp des Felds. Dies kann einen ODBC-SQL-Datentyp oder die treiberspezifischen SQL-Datentyp sein. Eine Liste der gültigen ODBC-SQL-Datentypen finden Sie unter "SQL Data Types" im Windows SDK. Informationen zu Treiber-spezifische SQL-Datentypen finden Sie in der vom Treiber-Dokumentation.

*m_nPrecision*<br/>
Die maximale Genauigkeit des Felds. Weitere Informationen finden Sie unter "Genauigkeit, Dezimalstellen, Länge und Größe" im Windows SDK.

*m_nScale*<br/>
Die Dezimalstellen des Felds. Weitere Informationen finden Sie unter "Genauigkeit, Dezimalstellen, Länge und Größe" im Windows SDK.

*m_nNullability*<br/>
Gibt an, ob das Feld einen Null-Wert akzeptiert. Dies kann einen von zwei Werten sein: SQL_NULLABLE, wenn das Feld Null-Werte lässt oder Null-Werte SQL_NO_NULLS, wenn das Feld nicht akzeptiert.

## <a name="remarks"></a>Hinweise

Um diese Informationen abzurufen, rufen [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).

## <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)<br/>
[CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)
