---
title: CODBCFieldInfo-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CODBCFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88bcac3c7ce4658ec7dafeaa1cac45b5f2450298
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370733"
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
 `m_strName`  
 Der Name des Felds.  
  
 *m_nSQLType*  
 Der SQL-Datentyp des Felds. Dies kann einen ODBC-SQL-Datentyp oder treiberspezifischen SQL-Datentyp sein. Eine Liste der gültigen ODBC SQL-Datentypen finden Sie unter "SQL-Datentypen" im Windows SDK. Informationen zu treiberspezifischen SQL-Datentypen finden Sie unter der Treiber-Dokumentation.  
  
 *m_nPrecision*  
 Die maximale Genauigkeit des Felds. Weitere Informationen finden Sie unter "Genauigkeit, Dezimalstellen, Länge und Anzeigegröße" im Windows SDK.  
  
 *m_nScale*  
 Die Dezimalstellen des Felds. Weitere Informationen finden Sie unter "Genauigkeit, Dezimalstellen, Länge und Anzeigegröße" im Windows SDK.  
  
 *m_nNullability*  
 Gibt an, ob das Feld einen Null-Wert akzeptiert. Dies kann eine von zwei Werten: **SQL_NULLABLE** , wenn das Feld Null-Werte akzeptiert oder **SQL_NO_NULLS** , wenn das Feld keine Null-Werte annimmt.  
  
## <a name="remarks"></a>Hinweise  
 Um diese Informationen abzurufen, rufen Sie [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset:: GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)


