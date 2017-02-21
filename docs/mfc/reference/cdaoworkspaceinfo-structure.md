---
title: "CDaoWorkspaceInfo-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoWorkspaceInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoWorkspaceInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), Arbeitsbereicheauflistung"
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoWorkspaceInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoWorkspaceInfo`\-Struktur enthält Informationen über einen Arbeitsbereich, der für den Datenbankzugriff Datenzugriffsobjekt \(dao\)\- definiert ist.  
  
## Syntax  
  
```  
  
      struct CDaoWorkspaceInfo  
{  
   CString m_strName;           // Primary  
   CString m_strUserName;       // Secondary  
   BOOL m_bIsolateODBCTrans;    // All  
};  
```  
  
#### Parameter  
 `m_strName`  
 Benennt das eindeutig Arbeitsbereichsobjekt.  Um den Wert dieser Eigenschaft direkt abrufen, rufen Sie die [GetName](../Topic/CDaoQueryDef::GetName.md)\-Memberfunktion des Querydef\-Objekts auf.  Weitere Informationen finden Sie im Thema "Name\-Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_strUserName*  
 Ein Wert, der den Besitzer eines Arbeitsbereichsobjekts darstellt.  Weitere Informationen finden Sie im Thema "Benutzernamen\-Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_bIsolateODBCTrans*  
 Ein Wert, der angibt, ob mehrere Transaktionen, die dieselbe ODBC\-Datenbank betreffen, sind isoliert.  Weitere Informationen finden Sie unter [CDaoWorkspace::SetIsolateODBCTrans](../Topic/CDaoWorkspace::SetIsolateODBCTrans.md).  Weitere Informationen finden Sie im Thema "IsolateODBCTrans\-Eigenschaft" in der DAO\-Hilfe.  
  
## Hinweise  
 Der Arbeitsbereich ist ein Objekt der Klasse [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md).  Die Verweise auf primärem, und einen sekundären alle oben geben an, wie die Informationen durch die [GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md)\-Memberfunktion in der `CDaoWorkspace`\- Klasse zurückgegeben werden.  
  
 Die Informationen, die von der [CDaoWorkspace::GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md)\-Memberfunktion aufgerufen werden, werden in einer `CDaoWorkspaceInfo`\-Struktur gespeichert.  `CDaoWorkspaceInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoWorkspaceInfo`\-Objekts zu speichern.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)