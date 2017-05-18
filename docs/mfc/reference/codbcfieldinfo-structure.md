---
title: CODBCFieldInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CODBCFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- ODBC, data source information
- CODBCFieldInfo structure
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1080eb323c599014d84acab94aee4622795fdb96
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

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
 Der SQL-Datentyp des Felds. Dies kann eine ODBC SQL-Datentyp oder treiberspezifischen SQL-Datentyp sein. Eine Liste der gültigen ODBC SQL-Datentypen, finden Sie unter "SQL-Datentypen" in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Informationen zu treiberspezifischen SQL-Datentypen finden Sie in der Treiber-Dokumentation.  
  
 *m_nPrecision*  
 Die maximale Genauigkeit des Felds. Weitere Informationen finden Sie unter "Genauigkeit, Dezimalstellen, Länge und Größe" in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m_nScale*  
 Die Dezimalstellen des Felds. Weitere Informationen finden Sie unter "Genauigkeit, Dezimalstellen, Länge und Größe" in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m_nNullability*  
 Gibt an, ob das Feld einen Null-Wert akzeptiert. Dies kann eine der zwei Werte: **SQL_NULLABLE** , wenn das Feld Null-Werte annimmt oder **SQL_NO_NULLS** , wenn das Feld keine Null-Werte zulässt.  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie zum Abrufen dieser Informationen [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset:: GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)



