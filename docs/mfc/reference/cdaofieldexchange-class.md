---
title: "CDaoFieldExchange Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoFieldExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoFieldExchange class"
  - "DAO (Datenzugriffsobjekte), record field exchange (DFX)"
  - "DFX (DAO-Datensatzfeldaustausch)"
  - "DFX (DAO-Datensatzfeldaustausch), DAO Record Field Exchange"
  - "exchanging data between databases and recordsets"
  - "field exchange"
  - "field exchange, record for DAO classes"
  - "RFX (Datensatzfeldaustausch)"
  - "RFX (Datensatzfeldaustausch), DAO-Klassen"
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoFieldExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt die Routinen des DAO\-Datensatzfeldaustauschs \(DFX\), die von der DAO\-Datenbankklassen verwendet werden.  
  
## Syntax  
  
```  
class CDaoFieldExchange  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDaoFieldExchange::IsValidOperation](../Topic/CDaoFieldExchange::IsValidOperation.md)|Gibt Wert ungleich 0 zurück, wenn der aktuelle Vorgang für den Typ des Felds aus, das aktualisiert wird.|  
|[CDaoFieldExchange::SetFieldType](../Topic/CDaoFieldExchange::SetFieldType.md)|Gibt den Typ des Recordsetdatenmembers \- Spalte oder \- Parameter dargestellt durch alle nachfolgenden Aufrufe der DFX\-Funktionen bis zum nächsten Aufruf `SetFieldType` an.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDaoFieldExchange::m\_nOperation](../Topic/CDaoFieldExchange::m_nOperation.md)|Der DFX\-Vorgang, der durch den aktuellen Aufruf der \- Memberfunktion des Recordsets `DoFieldExchange` ausgeführt wird.|  
|[CDaoFieldExchange::m\_prs](../Topic/CDaoFieldExchange::m_prs.md)|Ein Zeiger auf das Recordset, auf dem DFX\-Vorgänge ausgeführt werden.|  
  
## Hinweise  
 `CDaoFieldExchange` hat keine Basisklasse.  
  
 Verwenden Sie diese Klasse, wenn Sie Datenaustauschroutinen für benutzerdefinierte Datentypen schreiben; andernfalls verwenden Sie nicht direkt diese Klasse.  DFX\-Austauschdaten zwischen den Felddatenmembern des [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)\-Objekts und die entsprechenden Felder des aktuellen Datensatzes in der Datenquelle.  DFX verwaltet den Austausch in beide Richtungen, von der Datenquelle und an die Datenquelle.  Siehe [Technischer Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) für Informationen zu benutzerdefinierten DFX Routinen zum Schreiben.  
  
> [!NOTE]
>  Die DAO\-Datenbankklassen sind von den MFC\-Datenbankklassen auf Grundlage Open Database Connectivity \(ODBC\) unterschiedlich.  Alle DAO\-Datenbankklassen\-Namen haben das Präfix "CDao".  Sie können auf ODBC\-Datenquellen mit den DAO\-Klassen noch zugreifen.  Im Allgemeinen sind die MFC\-Klassen auf Grundlage DAO besser geeignet als die MFC\-Klassen auf Grundlage ODBC.  Die DAO\-basierten Klassen machen die Daten ein und enthalten durch ODBC\-Treiber, über ein eigenes Datenbankmodul.  Sie unterstützen auch Operationen der Datendefinitionssprache \(Data Definition Language\), wie das Hinzufügen von Tabellen zu Klassen, statt sich DAO aufrufen zu müssen.  
  
> [!NOTE]
>  DAO\-Datensatzfeldaustausch \(DFX\) entspricht dem Datensatzfeldaustausch \(RFX\) in den ODBC\-basierten MFC\-Datenbankklassen \(`CDatabase`, `CRecordset`\) sehr ähnlich.  Wenn Sie RFX verstehen, ist es bedienungsfreundliches DFX.  
  
 Ein `CDaoFieldExchange`\-Objekt stellt die Kontextinformationen bereit, die erforderlich sind, damit DAO\-Datensatzfeldaustausch stattfindet.  `CDaoFieldExchange`\-Objekte unterstützen einige Operationen, einschließlich Bindungsparameter und Felddatenmembern und das Festlegen unterschiedlicher Flags für die Felder des aktuellen Datensatzes.  DFX\-Vorgänge werden auf Recordsetklassendatenmember von Typen ausgeführt, die von `enum`**FieldType** in `CDaoFieldExchange` definiert werden.  Mögliche Werte sind: **FieldType**  
  
-   **CDaoFieldExchange::outputColumn** für Felddatenmember.  
  
-   **CDaoFieldExchange::param** für Parameterdatenmember.  
  
 Die [IsValidOperation](../Topic/CDaoFieldExchange::IsValidOperation.md)\-Memberfunktion wird für das Schreiben eigener Routinen der benutzerdefinierten DFX bereitgestellt.  Sie verwenden [SetFieldType](../Topic/CDaoFieldExchange::SetFieldType.md) häufig in den [CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)\-Funktionen.  Ausführliche Informationen über die globalen Funktionen DFX, finden Sie unter [Datensatzfeldaustausch\-Funktionen](../../mfc/reference/record-field-exchange-functions.md).  Informationen zu benutzerdefinierten DFX Routinen zum Schreiben für eigene Datentypen, finden Sie unter [Technischer Hinweis 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
## Vererbungshierarchie  
 `CDaoFieldExchange`  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)