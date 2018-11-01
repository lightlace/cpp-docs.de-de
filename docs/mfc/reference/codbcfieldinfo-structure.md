---
title: CODBCFieldInfo-Struktur
ms.date: 11/04/2016
f1_keywords:
- CODBCFieldInfo
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
ms.openlocfilehash: 5ad7d8f710c763b25771e3d1fa8839b5b64802ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655272"
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
[CRecordset:: GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)

