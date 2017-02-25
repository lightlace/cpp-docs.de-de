---
title: "CDaoDatabaseInfo-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoDatabaseInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoDatabaseInfo-Struktur"
  - "DAO (Datenzugriffsobjekte), Datenbankauflistung"
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# CDaoDatabaseInfo-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CDaoDatabaseInfo`\-Struktur enthält Informationen über ein Datenbankobjekt, das für Datenzugriffsobjekte \(DAO\) definiert ist.  
  
## Syntax  
  
```  
  
      struct CDaoDatabaseInfo  
{  
   CString m_strName;       // Primary  
   BOOL m_bUpdatable;       // Primary  
   BOOL m_bTransactions;    // Primary  
   CString m_strVersion;    // Secondary  
   long m_lCollatingOrder;  // Secondary  
   short m_nQueryTimeout;   // Secondary  
   CString m_strConnect;    // All  
};  
```  
  
#### Parameter  
 `m_strName`  
 Benennt eindeutig das Datenbankobjekt.  Um diese Eigenschaft direkt abrufen, rufen Sie [CDaoDatabase::GetName](../Topic/CDaoDatabase::GetName.md) auf.  Ausführliche Informationen finden Sie im Thema "Name\-Eigenschaft" in der DAO\-Hilfe.  
  
 `m_bUpdatable`  
 Gibt an, ob Änderungen vorgenommen werden können an der Datenbank.  Um diese Eigenschaft direkt abrufen, rufen Sie [CDaoDatabase::CanUpdate](../Topic/CDaoDatabase::CanUpdate.md) auf.  Ausführliche Informationen finden Sie im Thema "aktualisierbare Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_bTransactions*  
 Gibt an, ob eine Datenquelle Transaktionen \- die Aufzeichnung eine Reihe von Änderungen unterstützt, die später zurücksetzen \(abgebrochen oder übergeben werden können \(gespeichert wurde\).  Wenn eine Datenbank auf Grundlage das Microsoft Jet\-Datenbankmodul ist, ist die Transaktionseigenschaft ungleich 0 \(null\) und Sie können Transaktionen verwenden.  Andere Datenbankmodule möglicherweise nicht unterstützen Transaktionen.  Um diese Eigenschaft direkt abrufen, rufen Sie [CDaoDatabase::CanTransact](../Topic/CDaoDatabase::CanTransact.md) auf.  Ausführliche Informationen finden Sie im Thema "Transaktions\-Eigenschaft" in der DAO\-Hilfe.  
  
 *m\_strVersion*  
 Gibt die Version des Microsoft Jet\-Datenbankmoduls an.  Um den Wert dieser Eigenschaft direkt abrufen, rufen Sie die [GetVersion](../Topic/CDaoDatabase::GetVersion.md)\-Memberfunktion des Datenbankobjekts auf.  Ausführliche Informationen finden Sie im Thema "Versions\-Eigenschaft" in der DAO\-Hilfe.  
  
 `m_lCollatingOrder`  
 Gibt der Sequenz der Sortierreihenfolge im Text für Zeichenfolgenvergleiche oder Sortierung an.  Mögliche Werte:  
  
-   **dbSortGeneral** verwendet die allgemeine \(Deutsch, Englisch, Französisch, portugiesisches, Italienisch und Spanisch\) modernes Sortierreihenfolge.  
  
-   **dbSortArabic** verwendet die arabische Sortierreihenfolge.  
  
-   **dbSortCyrillic** verwendet die Russisch Sortierreihenfolge.  
  
-   **dbSortCzech** verwendet die tschechische Sortierreihenfolge.  
  
-   **dbSortDutch**  verwendet die niederländische Sortierreihenfolge.  
  
-   **dbSortGreek** verwendet die griechische Sortierreihenfolge.  
  
-   **dbSortHebrew** verwendet die hebräische Sortierreihenfolge.  
  
-   **dbSortHungarian** verwendet die ungarische Sortierreihenfolge.  
  
-   **dbSortIcelandic** verwendet die isländische Sortierreihenfolge.  
  
-   **dbSortNorwdan** verwendet die norwegische oder Dänisch Sortierreihenfolge.  
  
-   **dbSortPDXIntl** verwendet die Internationalsortierreihenfolge Paradox.  
  
-   **dbSortPDXNor** mit norwegische oder Dänisch Sortierreihenfolge des Paradoxes.  
  
-   Schwedisch **dbSortPDXSwe** Verwendung oder finnische Sortierreihenfolge des Paradoxes.  
  
-   **dbSortPolish** verwendet die polnische Sortierreihenfolge.  
  
-   **dbSortSpanish** verwendet die spanische Sortierreihenfolge.  
  
-   **dbSortSwedFin** verwendet die Schwedisch oder finnische Sortierreihenfolge.  
  
-   **dbSortTurkish** verwendet die türkische Sortierreihenfolge.  
  
-   **dbSortUndefined** Die Sortierreihenfolge wird oder unbekannt undefiniert.  
  
 Weitere Informationen finden Sie im Thema ", Windows\-Registrierungseinstellungen für Datenzugriff" in der DAO\-Hilfe anzupassen.  
  
 *m\_nQueryTimeout*  
 Die Anzahl von Sekunden, die das Microsoft Jet\-Datenbankmodul wartet, bevor ein Timeoutfehler auftritt, wenn eine Abfrage auf eine ODBC\-Datenbank ausgeführt wird.  Der Standardtimeoutwert ist 60 Sekunden.  Wenn QueryTimeout auf 0 festgelegt ist, tritt kein Timeout auf; Dies kann das Programm führen mehr reagiert.  Um den Wert dieser Eigenschaft direkt abrufen, rufen Sie die [GetQueryTimeout](../Topic/CDaoDatabase::GetQueryTimeout.md)\-Memberfunktion des Datenbankobjekts auf.  Ausführliche Informationen finden Sie im Thema "QueryTimeout\-Eigenschaft" in der DAO\-Hilfe.  
  
 `m_strConnect`  
 Stellt Informationen zu Quelle einer geöffneten Datenbank.  Informationen zu schließen Sie Zeichenfolgen und nach Informationen über den Wert dieser Eigenschaft direkt abrufen, finden die Memberfunktion [CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md) an.  Weitere Informationen finden Sie im Thema "Connect\-Eigenschaft" in der DAO\-Hilfe.  
  
## Hinweise  
 Die Datenbank ist ein DAO\-Objekt, das ein MFC\-Objekt der Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) zugrunde liegt.  Die Verweise auf primärem, und einen sekundären alle oben geben an, wie die Informationen durch die [CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md)\-Memberfunktion zurückgegeben werden.  
  
 Die Informationen, die von der [CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md)\-Memberfunktion aufgerufen werden, werden in einer `CDaoDatabaseInfo`\-Struktur gespeichert.  Aufruf `GetDatabaseInfo` für das `CDaoWorkspace`\-Objekt, in dessen Datenbankauflistung das Datenbankobjekt gespeichert wird.  `CDaoDatabaseInfo` definiert auch eine `Dump`\-Memberfunktion in Debugbuilds.  Sie können `Dump` verwenden, um den Inhalt eines `CDaoDatabaseInfo`\-Objekts zu speichern.  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace::GetDatabaseCount](../Topic/CDaoWorkspace::GetDatabaseCount.md)