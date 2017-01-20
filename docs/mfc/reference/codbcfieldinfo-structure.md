---
title: "CODBCFieldInfo-Struktur"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CODBCFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CODBCFieldInfo-Struktur"
  - "ODBC, Datenquelleninformationen"
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CODBCFieldInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CODBCFieldInfo`\-Struktur enthält Informationen über die Felder in einer ODBC\-Datenquelle.  
  
## Syntax  
  
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
  
#### Parameter  
 `m_strName`  
 Der Name des Felds.  
  
 *m\_nSQLType*  
 Der SQL\-Datentyp des Felds.  Dieser kann ein ODBC SQL\-Datentyp oder ein treiberspezifischer SQL\-Datentyp sein.  Eine Liste gültiger ODBC SQL\-Datentypen, siehe "SQL\-Datentypen" in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Informationen zum treiberspezifische SQL\-Datentypen, finden Sie in der Dokumentation des Treibers.  
  
 *m\_nPrecision*  
 Die maximale Genauigkeit des Felds.  Ausführliche Informationen finden Sie unter "Genauigkeit, Dezimalstellen, Länge und Anzeigen\-Größe" in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m\_nScale*  
 Die Skala des Felds.  Ausführliche Informationen finden Sie unter "Genauigkeit, Dezimalstellen, Länge und Anzeigen\-Größe" in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m\_nNullability*  
 Ob das Feld einen NULL\-Wert akzeptiert.  Dieser kann zwei Werte sein: **SQL\_NULLABLE**, wenn das Feld NULL\-Werte akzeptiert oder **SQL\_NO\_NULLS**, wenn das Feld keine NULL\-Werte akzeptiert.  
  
## Hinweise  
 Um diese Informationen zu erhalten, rufen Sie [CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md) auf.  
  
## Anforderungen  
 **Header:** afxdb.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md)   
 [CRecordset::GetFieldValue](../Topic/CRecordset::GetFieldValue.md)