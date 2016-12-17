---
title: "CFieldExchange Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CFieldExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFieldExchange class"
  - "Datentypen [C++], Benutzerdefiniert"
  - "enum FieldType"
  - "enum FieldType, CFieldExchange"
  - "FieldType enumeration"
  - "RFX (record field exchange) [C++]"
  - "RFX (record field exchange) [C++], classes for"
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: 24
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CFieldExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt die Routinen für den Datensatzfeldaustausch \(RFX\) und mithilfe des Sammel\-Datensatzfeldaustauschs \(Bulk\-RFX\), die durch die Datenbankklassen verwendet werden.  
  
## Syntax  
  
```  
  
class CFieldExchange  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CFieldExchange::IsFieldType](../Topic/CFieldExchange::IsFieldType.md)|Gibt Wert ungleich 0 zurück, wenn der aktuelle Vorgang für den Typ des Felds aus, das aktualisiert wird.|  
|[CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md)|Gibt den Typ des Recordsetdatenmembers \- Spalte oder \- Parameter dargestellt durch alle nachfolgenden Aufrufe der RFX\-Funktionen bis zum nächsten Aufruf `SetFieldType` an.|  
  
## Hinweise  
 `CFieldExchange` hat keine Basisklasse.  
  
 Verwenden Sie diese Klasse, wenn Sie Datenaustauschroutinen für benutzerdefinierte Datentypen schreiben, oder wenn Sie das gesammelte Abrufen von Zeilen implementiert; andernfalls verwenden Sie nicht direkt diese Klasse.  RFX und Massen\-RFX\-Austauschdaten zwischen den Felddatenmembern des Recordset\-Objekts und die entsprechenden Felder des aktuellen Datensatzes in der Datenquelle.  
  
> [!NOTE]
>  Wenn Sie mit den Datenzugriffsobjekten \(DAO\) Klasse anstatt die Klassen der Open Database Connectivity \(ODBC\), Verwendungsklasse [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) stattdessen arbeiten.  Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank\-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Ein `CFieldExchange`\-Objekt stellt die Kontextinformationen zur Verfügung, die damit Datensatzfeldaustausch oder den Sammel\-Datensatzfeldaustausch erforderlich sind, stattfindet.  `CFieldExchange`\-Objekte unterstützen einige Operationen, einschließlich Bindungsparameter und Felddatenmembern und das Festlegen unterschiedlicher Flags für die Felder des aktuellen Datensatzes.  RFX und Massen\-RFX\-Vorgänge werden auf Recordsetklassendatenmember von Typen ausgeführt, die von `enum`**FieldType** in `CFieldExchange` definiert werden.  Mögliche Werte sind: **FieldType**  
  
-   **CFieldExchange::outputColumn** für Felddatenmember.  
  
-   **CFieldExchange::inputParam** oder **CFieldExchange::param** für Eingabeparameterdatenmember.  
  
-   **CFieldExchange::outputParam** für Ausgabeparameterdatenmember.  
  
-   **CFieldExchange::inoutParam** für Eingabe\/Ausgabe\-Parameterdatenmember.  
  
 Die meisten der Memberfunktionen und Datenmember der Klasse werden für das Schreiben eigener Routinen der benutzerdefinierten RFX bereitgestellt.  Sie verwenden `SetFieldType` häufig.  Weitere Informationen finden Sie in Artikel [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md) und [Recordsets \(ODBC\)](../../data/odbc/recordset-odbc.md).  Informationen über das gesammelte Abrufen von Zeilen, finden Sie im Artikel [Recordset: Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  Ausführliche Informationen über die globalen Funktionen RFX und der Großteil RFX, finden Sie unter [Datensatzfeldaustausch\-Funktionen](../../mfc/reference/record-field-exchange-functions.md) im MFC\-Makro\- und \-Werteabschnitt diesem Verweis.  
  
## Vererbungshierarchie  
 `CFieldExchange`  
  
## Anforderungen  
 **Header:** afxdb.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)