---
title: "CDaoErrorInfo-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CDaoErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoErrorInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), Fehlerauflistung"
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
caps.latest.revision: 13
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoErrorInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoErrorInfo`\-Struktur enthält Informationen zu einem Fehlerobjekt, das für Datenzugriffsobjekte \(DAO\) definiert ist.  
  
## Syntax  
  
```  
  
      struct CDaoErrorInfo  
{  
   long m_lErrorCode;  
   CString m_strSource;  
   CString m_strDescription;  
   CString m_strHelpFile;  
   long m_lHelpContext;  
};  
```  
  
#### Parameter  
 *m\_lErrorCode*  
 Ein numerischer DAO\-Fehlercode.  Siehe das Thema "auffangbare Datenzugriffs\-Fehler" in der DAO\-Hilfe.  
  
 *m\_strSource*  
 Der Name des Objekts oder der Anwendung, die ursprünglich den Fehler generieren.  Die Eigenschaft gibt einen Zeichenfolgenausdruck an, der das Objekt darstellt, das ursprünglich den Fehler generiert wurde; der Ausdruck ist normalerweise der Klassenname des Objekts.  Ausführliche Informationen finden Sie im Thema "Quelleigenschaft" in der DAO\-Hilfe.  
  
 *m\_strDescription*  
 Eine beschreibende Zeichenfolge zugeordnet mit einem Fehler.  Ausführliche Informationen finden Sie im Thema "Beschreibungs\-Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_strHelpFile*  
 Ein vollqualifizierter Pfad zu einer Microsoft Windows\-Hilfedatei.  Ausführliche Informationen finden Sie im Thema "HelpContext, HelpFile\-Eigenschaften" in der DAO\-Hilfe.  
  
 *m\_lHelpContext*  
 Eine Kontext\-ID für ein Thema in einer Microsoft Windows\-Hilfedatei.  Ausführliche Informationen finden Sie im Thema "HelpContext, HelpFile\-Eigenschaften" in der DAO\-Hilfe.  
  
## Hinweise  
 MFC kapselt nicht DAO\-Fehlerobjekte in einer Klasse.  Stattdessen stellt die [CDaoException](../../mfc/reference/cdaoexception-class.md)\-Klasse eine Schnittstelle für die Fehlerauflistung, die im Objekt DAO **DBEngine** , das Objekt enthält, das auch alle Arbeitsbereiche enthält.  Wenn ein Vorgang MFC DAO ein `CDaoException`\-Objekt aus, dem Sie catch, MFC eine `CDaoErrorInfo`\-Struktur ausfüllen und im [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md)\-Member des Ausnahmeobjekts speichern. \(Wenn Sie festlegen, dass DAO direkt aufzurufen, muss die Memberfunktion [GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md) des Ausnahmeobjekts selbst aufrufen, um `m_pErrorInfo` auszufüllen.\)  
  
 Weitere Informationen zum Behandeln von DAO\-Fehlern, finden Sie im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  Weitere Informationen finden Sie im Thema "Fehler\-Objekt" in der DAO\-Hilfe.  
  
 Die Informationen, die von der [CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md)\-Memberfunktion aufgerufen werden, werden in einer `CDaoErrorInfo`\-Struktur gespeichert.  Überprüfen Sie den Datenmember [m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md) von einem `CDaoException`\-Objekt, das Sie in einem Ausnahmehandler abfangen, oder rufen Sie `GetErrorInfo` von einem `CDaoException`\-Objekt, das Sie erstellen explizit, um Fehler zu überprüfen, die möglicherweise aufgetreten während eines direkten Aufrufs dem DAO, verbindet.  `CDaoErrorInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoErrorInfo`\-Objekts zu speichern.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)